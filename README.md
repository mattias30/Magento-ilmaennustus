Juhised:
  0. Enne alustamist on vajalik Dockeri olemasolu. Saab laadida siit: https://www.docker.com/get-started/.
    Pärast Dockeri laadimist muuta seadetes ressursikasutust ning kõik seaded viia poole peale või kõrgemale. 
    Kui on tegemist WSL integratsiooniga, tuleb luua fail .wslconfig (kui puudub) ning lisada järgnev:
    [wsl2]
    memory=10GB   # Or 8GB, 10GB, etc., depending on your system RAM. Don't allocate all of it.
    processors=10 # Adjust to the number of CPU cores you want to allocate
    swap=4       # Optional: Disable swap for WSL2 if you have enough RAM
    localhostForwarding=true # Usually default, but good to have
    
  1. Luua uus kaust ja siseneda sellesse.
  2. Terminalis käivitada kood: curl -s https://raw.githubusercontent.com/mattias30//Magento-ilmaennustus/master/lib/template | bash
  3. Käivitada: bin/download community 2.4.7-p5
  4. Käivitada: bin/setup magento.test
  5. veebibrauseris liikuda lehele: https://magento.test
     Juhul kui veebilehte ei leita ja tegemist on WSL Dockeriga, tuleks hostmasina host faili lisada rida: 127.0.0.1 magento.test
