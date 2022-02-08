# Blokų grandinų technologijos, antra užduotis: Supaprastintos blokų grandinės (blockchain) kūrimas.

## Užduoties formuluotė
* Sugeneruoti ~1000 tinklo vartotojų (aka user'ių), kurie turėtų bent tris atributus:
vardą,
viešąjį hash raktą (public_key)
tam tikros valiutos atsitiktinį balansą (pvz., nuo 100 iki 1000000 valiutos vienetų).
* Sugeneruoti ~10000 naujų, į jokį bloką dar neįdėtų, transakcijų pool'ą, o transakcijos turėtų bent šiuos atributus:
transakcijos ID (kitų transakcijos laukų hash'as),
siuntėjas (jo viešasis raktas)
gavėjas (jo viešasis raktas)
suma
* Iš transakcijų pool'o atsitiktinai pasirinkti 100-ą transakcijų, kurias bandysime įdėti į naują bloką (tarsime, kad naujas blokas talpins apie
100 transakcijų). Reikiama bloko struktūra ir būtini atributai pateikti paveiksle aukščiau.
* Realizuokite naujų blokų kasimo (angl. mining) Proof-of-Work (PoW) tipo procesą, kurio tikslas yra surasti naujam blokui hash'ą, tenkinantį
Difficulty Targer reikalavimą, t.y., hash'o pradžioje esančių nulių tam tikrą skaičių. Nulių skaičius priklauso nuo Jūsų sukurto hash
funkcijos savybių ir efektyvumo. Paeksperimentuokite, kad tai neužtruktų per ilgai. Kaip matyti, bloko kasimui yra reikalingas transakcijų
Merkle hash'as, kuris taip pat turi būti realizuotas (žr. detalizaciją versijų reikalavimuose).
* Suradus tokį naujo bloko hash'ą:
į naują bloką priskirtas transakcijas ištrinkite iš transakcijų pool'o;
"įvykdykite" transakcijas, t.y., atnaujinkite tinklo vartotojų balansus;
naują bloką pridėkite prie blockchain grandinės.
* Kartoti 3-5 žingsnius tol, kol yra laisvų transakcijų. Galima būtų įtraukti ir visus 1-5 žingsnius, tokiu būdu įtraukiant naujų vartotojų ir/ar
transakcijų kūrimą, o ciklą stabdyti naudojantis kitomis logiškomis sąlygomis.

## Programos paleidimas
* Atsisiųsti programos kodą iš "releases";
* Kodą išarchyvuoti naujame aplanke;
* Aplanką atsidaryti naudojantis Jums patinkantį IDE, arba terminalą (pavaizduota apačioje).




![image](https://user-images.githubusercontent.com/78842398/152876688-05ffba81-0197-4ba2-a969-c37f1c8d8d0a.png)
* Kodą sukompiliuoti, o po to paleisti .exe failą naudojantis šias komandas:

```
g++ main.cpp functions.cpp md5.cpp -o programa
```
```
./programa
```


## Programos išvedama informacija

```
.
..
...
----------------------------------------------------------------------
Block hash: 00082bf3fb04b281e1a896dedd82efdc
Previous block hash: 00093b90907528d594829ff95df4ab33
Timestamp: -692173541
Transaction number: 100
Difficulty: 15794176
Merkle root hash: 46db21e39f65471333730b58e9f25cdd
Version: 1
Nonce: 2525
Transactions volume: 751413

Transactions
--------------------------------------------------
Transaction ID: e278c372f796b3c8e8d3d29761d9d57971b6e19693e4c0a5f695d1e284e0a9d6
Sender public key: d9e3b6e9b5a4d5f7c8c38299d3a178d3b19299c6e3c4a4929076f86763e7d3d0
Receiver public key: b4a386b4e6d7b1b1a8c179e28662e1c3a9a180a970b1e173b389a1e1a6c28773
Transaction amount: 21323
.
..
...
```


```
...
..
.
----------------------------------------------------------------------
Transaction ID: e8617064b6c1b7b8a776f2f9a2d4e7a4e97375e6f5d5c3f1d662d5f898a2f670
Sender public key: b183c769c5b296c2877168837161e894a99079648367b96564d1a58493a2d8a5
Receiver public key: 88e889d891e1e372e4e193e7e9b591e789a1f1c794e6b1a86486d47897e163b6
Transaction amount: 14138
----------------------------------------------------------------------
Transaction ID: d7f08972d274a9d290b0d9746896e570a9d7a9e961b2d866b479c0f472b3f6c1
Sender public key: d989a685a1a175f292c9e6b7d9a4e4c39592b3f0c4876894b076d7a485828679
Receiver public key: c473b4f680d470d3918799b076f2f3f694f87864f76584f8a5c6e091b0b8a367
Transaction amount: 3064
----------------------------------------------------------------------
.
..
...
```

```
...
..
.
----------------------------------------------------------------------
Name: member5
Public key: d5e7e28773b361999282d0e67395a3c1d4816160a093f481a3a8f2b1976186b2
Balance: 4803
----------------------------------------------------------------------
Name: member6
Public key: c5c6c9e368d5d2a466a8a6a6e7a26973c879a288f7f376d377a664a4a9a7a769
Balance: 28035
----------------------------------------------------------------------
.
..
...
```

