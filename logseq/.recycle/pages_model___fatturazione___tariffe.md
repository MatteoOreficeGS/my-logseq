tags:: [[Models/Type/Data Model/Entity]]

- # DDL
	- ```sql
	  create table tariffe
	  (
	      id                    int unsigned auto_increment
	          primary key,
	      nome                  varchar(255)                                    not null,
	      corriere              tinyint unsigned                                not null,
	      zone_incluse          text                                            not null,
	      chiave_primaria       tinyint unsigned                                not null,
	      tipo_servizio         varchar(16)                                     not null,
	      consegna_particolare  varchar(16)                                     not null,
	      addebito              varchar(16)                                     not null,
	      addebito_speciale     varchar(16)                                     not null,
	      addebito_speciale_txt varchar(255)                                    not null,
	      addebito_istat        decimal(4, 2)                                   not null,
	      owner                 mediumint                  default 0            not null,
	      peso_minimo           decimal(8, 1)              default 0.0          not null,
	      peso_massimo          decimal(8, 1)              default 99999.0      not null,
	      documenti             tinyint                    default 0            not null,
	      multicollo            enum ('N', 'S', 'E')       default 'E'          not null,
	      inizio_validita       date                       default '0000-00-00' not null,
	      fine_validita         date                       default '0000-00-00' not null,
	      tariffa_import        tinyint(1)                 default 0            not null,
	      uso_listino           enum ('attivo', 'passivo') default 'passivo'    not null,
	      assegna_corriere      tinyint(1)                 default 1            not null,
	      addebito_minimo       decimal(10, 3)             default 0.000        not null,
	      flag_addebito_minimo  enum ('T', 'C', 'X')       default 'X'          not null,
	      nazione_partenza      varchar(255)                                    not null,
	      internazionale        tinyint(1)                 default 0            not null,
	      attivo                tinyint(1)                 default 0            not null,
	      codice_tariffa_brt    varchar(3)                                      null comment 'codice tariffa brt'
	  );
	  ```
	- Considerare che alcune colonne hanno senso solo in alcuni casi #CAUTION
	- ## `tariffa.tariffa_import`
		- Vale solo per spedizioni internazionali, quindi indica