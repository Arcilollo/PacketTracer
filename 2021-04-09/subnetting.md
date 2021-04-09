# Indirizzo di partenza

10.0.0.0/8

# Elenco sottoreti da creare

Arcidiacono = 11 lettere
Lorenzo 	= 7  lettere

sottorete 1: 11 * 100	= 1100
sottorete 2: 7 * 50		= 350
sottorete 3: 7 * 30		= 210
sottorete 4: 7 * 10		= 70

# Procedimento

subnetto l'indirizzo 10.0.0.0/8 in modo da ottenere una subnet che contenga almeno 1100 host, quindi prendo 13 bit dal campo di rete (la subnet ottenuta conterrá 2^11-2 = 2046 host) e ottengo la subnet 10.0.0.0/21

subnetto il secondo indirizzo ottenuto e ripeto cosí finché non ho "trovato" tutte le sottoreti

* 10.0.0.0/21 -> Sottorete 1 (1100/2046) 10.0.0.1 - 10.0.7.254
* 10.0.8.0/21
	* 10.0.8.0/22
		* 10.0.8.0/23 -> Sottorete 2 (350/510) 10.0.8.1 - 10.0.9.254
		* 10.0.10.0/23
			* 10.0.10.0/24 -> Sottorete 3 (210/254) 10.0.10.1 - 10.0.10.254
			* 10.0.11.0/24
				* 10.0.11.0/25 -> Sottorete 4 (70/126) 10.0.11.1 10.0.11.126
				* 10.0.11.128/25
	* 10.0.12.0/22
* 10.0.16.0/21
* 10.0.24.0/21
* ...
* 10.255.248.0/21
