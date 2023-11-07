# Risoluzione problematiche
- ```shell
  grep 'Risposta.*Rate.*15386' /tmp/CtrFatGsped.log | grep -oP 'cliente \d+' | sort -h | uniq
  ```