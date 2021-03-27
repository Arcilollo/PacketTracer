# Indirizzo di partenza

172.16.0.0/16

**Devo creare 3 subnet:**
1. Sottorete A: 50 host
2. Sottorete B: 200 host
3. Sottorete C: 510 host

# Creazione sottoreti

* 172.16.0.0/23 -> Sottorete C			172.16.0.1 -> 172.16.1.254
* 172.16.2.0/23
	* 172.16.2.0/24 -> Sottorete B		172.16.2.1 -> 172.16.2.254
	* 172.16.3.0/24
		* 172.16.3.0/26 -> Sottorete A	172.16.3.1 -> 172.16.3.62
			* 172.16.3.64/30 -> link 1
			* 172.16.3.68/30 -> link 2
