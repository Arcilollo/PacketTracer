# Obiettivi

### Creare le reti puno punto per i router

172.16.0.0/16 -> due sottoreti /30

### 10.0.0.0/8 -> 30 sottoreti (dalla 15esima)

* Sottorete 1: 500 host	-> 10.112.0.0/23
* Sottorete 2: 50 host	-> 10.112.2.128/26
* Sottorete 3: 120 host	-> 10.112.2.0/25
* Sottorete 4: 30 host	-> 10.112.2.192/27
* Sottorete 5: 10 host	-> 10.112.2.224/28

# Creazione reti punto punto (/30)

* 172.16.0.0/16 creo 16Ki reti /30
	* 172.16.0.0/30 -> da R1 a R2
	* 172.16.0.4/30 -> da R2 a R3
	* 172.16.0.8/30
	* ...
	* 172.16.255.252/30

# Creazione delle 30 sottoreti:

**10.0.0.0/8 // divido in 30 sottoreti e prendo la 15esima**

1. 10.00000|000.0.0/13 -> 10.0.0.0/13
2. 10.00001|000.0.0/13 -> 10.8.0.0/13
15. **10.01110|000.0.0/13 -> 10.112.0.0/13**
30. 10.11101|000.0.0/13 -> 10.232.0.0/13

# Subnetting variabile:

**prendo indirizzo 15esimo indirizzo trovato sopra e ci esegui il subnetting variabile**

* 10.112.0.0/13 // divido in 1024 sottoreti /23 da 510 host ciascuna
	* **10.112.0.0/23 -> Sottorete 1**
	* 10.112.2.0/23 // divido in 4 sottoreti /25 da 126 host ciascuna
		* **10.112.2.0/25 -> Sottorete 3**
		* 10.112.2.128/25 // divido in 2 sottoreti /26 da 62 host ciascuna
			* **10.112.2.128/26 -> Sottorete 2**
			* 10.112.2.192/26 // divido in 2 sottoreti /27 da 30 host ciascuna
				* **10.112.2.192/27 -> Sottorete 4**
				* 10.112.2.224/27 // divido in 2 sottoreti /28 da 14 host ciascuna
					* **10.112.2.224/28 -> Sottorete 5**
					* 10.112.2.240/28
		* 10.112.3.0/25
		* 10.112.3.128/25
	* ...
	* 10.119.254.0/23
