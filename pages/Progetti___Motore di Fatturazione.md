# Risoluzione problematiche
- ## Elencare i client id delle Rate per un'elaborazione
	- ```shell
	  grep 'Risposta.*Rate.*15386' /tmp/CtrFatGsped.log | \
	  	grep -oP 'cliente \d+' | \
	  	sort -h | uniq
	  ```
	- ```shell
	  grep 'Risposta.*Rate.*15386' /tmp/CtrFatGsped.log | \
	  	grep -oP 'Nessuna tariffa trovata per cliente \d+' | \
	  	sort -h | uniq
	  ```
	- ```shell
	  zgrep 'Risposta.*Rate.*15393' /tmp/CtrFatGsped.log | \
	  	grep -oP 'Rate response":"\K.*'
	  ```
-