tags:: #model/fatturazione/Accessorio

- Vedi anche #model/fatturazione/costi_accessori_local
- Vedi anche #model/fatturazione/costi_accessori_master
- # Scopo
	- Questa tabella é una **vista** che **unisce** le due tabelle di sopra in **override**
		- attenzione perché questa implementazione non é estesa a tutte le istanze ma solo implementata e testata su #client/Bonzai
			- https://gsped.atlassian.net/browse/FT-137
- # Nomi accessori
	- #+BEGIN_CAUTION
	  Notare che i nomi accessori a volte differiscono solo per il case, quindi il confronto deve avvernire 
	  #+END_CAUTION