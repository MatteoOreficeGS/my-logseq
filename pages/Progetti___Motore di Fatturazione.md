# #Troubleshooting
	- ## Elencare tutti i client id per cui non esiste una tariffa
		- ```shell
		  grep 'Risposta.*Rate.*15386' /tmp/CtrFatGsped.log | \
		  	grep -oP 'Nessuna tariffa trovata per cliente \d+' | \
		  	sort -h | uniq
		  ```
	- ## Mostrare tutte le risposte di un'elaborazione
		- ```shell
		  zgrep 'Risposta.*Rate.*15393' /tmp/CtrFatGsped.log | \
		  	grep -oP 'Rate response":"\K.*' | sort -h | uniq
		  ```
	- Esempio di codice PHP
	- ```php
	  
	    class Test {
	   	public function getTempiTransitoCorriere(array $sped,int $corriere): array|false
	      {
	          $this->log("Recupero tempi Rate del corriere " . $corriere);
	          switch ($corriere) {
	              case C_FEDEX:
	                  $this->load->model('FedExModel');
	                  $res = $this->FedExModel->getTempoTransito($sped,'array');
	                  break;
	              case C_UPS:
	                  $this->load->model('UPSModel');
	                  $res = $this->UPSModel->getTempoTransito($sped,'array');
	                  break;
	              case C_DHL:
	                  $this->load->model('DHLModel');
	                  $res = $this->DHLModel->getTempoTransito($sped,'array');
	                  /* Controllo se ci sono sconti da applicare */
	                  if (trim($sped['codice_sconto']) != "") {
	                      /* ciclo sui servizi */
	                      foreach ($res as $servizio => $datiRate) {
	                          /* dati trasporto temporaneo */
	                          $tmpSped = $sped;
	                          /* modifico il servizio */
	                          $tmpSped['servizio'] = $servizio;
	                          /* Creo oggetto trasporto */
	                          $trasporto = new Trasporto();
	                          $trasporto->setRecord($tmpSped);
	                          /* creo oggetto sconto */
	                          $sconto = $trasporto->getApplicabledDiscounts($sped['codice_sconto']);
	                          /* Verifico se sconto è valido e lo applico */
	                          if ($sconto) {
	                              $trasporto->isValidDiscount($sconto) && $realPrice = $trasporto->getDiscountedRate($sconto, $datiRate);
	                              /* Aggiorno i dati della rate */
	                              if ($realPrice) {
	                                  $res[$servizio] = $realPrice;
	                              }
	                          }
	                      }
	                  }
	                  break;
	              case C_GLOVO:
	                  $GlovoModelClassName = getProvider("courierConfig")->getCourierClassName(C_GLOVO);
	                  $GlovoModel = new $GlovoModelClassName();
	                  $trasporto = new Trasporto();
	                  $trasporto->setRecord($sped);
	                  $trasporto->setActiveQueryBuilder($this->db);
	                  $rate = $GlovoModel->getRate($trasporto);
	                  $res = false;
	                  if ($rate) {
	                      $res = [['totale' => $rate->estimateDelivery, 'nolo' => $rate->estimateDelivery]];
	                  }
	                  break;
	              default:
	                  return false;
	          }
	          return is_array($res) && sizeof($res) > 0 ? $res : false;
	      }
	  }
	  ```