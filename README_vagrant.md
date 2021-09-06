# SpotiClient-WebApp
Music streaming web app

## File inclusi

`vagrant.zip` : contiene il tutti i file `/vagrant` della macchina virtuale.

`vagrant.zip/LAMP-NodeJs/dump.sql` : contiene il dump di tutte le tabelle del database.

`Documentazione.pdf` : documentazione relativa al progetto.

`SpotiClient.apk`: l'apk generato con Cordova.

`cordovaApp.zip` : contiene tutti file relativi all'app cordova.

## Database
Il database con cui si interfaccia la web app è `Gruppo15`

L'utente con privilegi elevati si chiama `gruppo15_admin`

Tuttavia è possibile accedere anche attraverso `vagrantdb/vagrantdb`

## Avvio
All'avvio della macchina virtuale (`vagrant up`) verrà chiesto di scegliere quale interfaccia di rete la macchina dovrà usare:
Selezionare l'interfaccia Wi-Fi (`wlp3s0`)

Connettersi alla macchina virtuale (`vagrant ssh`)

- __Database__:
Posizionarsi in `/vagrant` e ripristinare il database eseguendo il comando:
```mysql -u vagrantdb -p < dump.sql```
ed inserendo come password `vagrantdb`.

- __Server__:
1. Posizionarsi in `/vagrant/www/`

2. Installare i moduli node necessari (`npm install`)

3. Avviare il server (`node server/server.js`)

- __Testing__:
Il server userà l'indirizzo statico 192.168.1.44 è starà in ascolto sulla porta 8080.
Per connettersi alla web app aprire l'indirizzo http://192.168.1.44:8080

###### Note
L'indirizzo ip del server può essere cambiato modificando la seguente riga del VagrantFile

```config.vm.network "public_network", ip: "192.168.1.44"```

La modifica dell'indirizzo ip del server, deve essere estesa anche all'app mobile generata con cordova, che vi si dovrà interfacciare, pertanto è consigliabile testare l'app mobile senza modificare l'ip del server.

