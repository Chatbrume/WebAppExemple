# WebAppExemple

## Platforme
https://docker.labs.eazytraining.fr/
login: devops
password: devops

## Création et installation
NEW INSTANCE of eazytraining/ansible
```cmd
sudo su admin
cd
git clone https://github.com/Chatbrume/WebAppExemple.git
```

NEW INSTANCE of eazytraining/client
```cmd
sudo su admin
cd
```

## build
Sur l'instance eazytraining/ansible

Modif de l'adresse ip
```cmd
vi prod.yml
```
Remplacer "10.0.13.4" par le numéro du eazytraining/client

Rappel commande vi:
Insert: taper sur la lettre i
Sauvegarder et quittez le fichier:
1) taper sur la touche echap
2) ecriver :wq
3) taper sur entrée

## ssh encrypte admin password
Encrypte le mots de pass admin:
`ansible-vault encrypt files/secrets/credential.vault`

Generer la clés rsa:
`ssh-keygen -t rsa`

Copier le ssh id du eazytraining/client (Remplacer "10.0.13.4" par le numéro du eazytraining/client):
`ssh-copy-id admin@10.0.13.4`

Lancer:
`ansible-playbook -i prod.yml deploy.yml`

## resultat
Sur l'instance eazytraining/client

Ouvrir le port 80
