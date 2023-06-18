# Toolumgebung

## Inhaltsverzeichnis

- [Toolumgebung](#Toolumgebung)
  - [Git](#git)
    - [Installation und Einrichtung](#installation-und-einrichtung)
  - [thema](#thema)
  - [thema](#thema-1)

## Git
### Installation und Einrichtung
1. Auf [GitHub](https://www.github.com) anmelden oder einen Account erstellen 
2. Ein neues Projekt erstellen
3. SSH-Key lokal mit folgendem Befehl erstellen: **ssh-keygen -t rsa -b 4096 -C "florian.brus@edu.tbz.ch"**
4. Datei %HOME%/.ssh/id_rsa.pub oder $HOME/.ssh/id_rsa.pub in Zwischenablage kopieren.
5. In GitHub in den Settings den eben kopierten SSH-Key hinzufügen
6. Git Client lokal installieren und mit folgenden Befehlen sein Projekt verknüpfen
- git config --global user.name "username"
- git config --global user.email "e-mail"
7. Anschliessend müssen wir noch unser Repository clonen, dies kann man mit folgenden Befehlen:
- cd Wohin/auch/immer
- git clone https://github.com/flobrus/M300-Services.git
- git pull
- git status
### Wichitge Befehle für Git
```Shell 
$  cd Pfad/zu/meinem/Repository    # Zum lokalen GitHub-Repository wechseln

$  git status                      # Geänderte Datei(en) werden rot aufgelistet
$  git add -A                      # Fügt alle Dateien zum "Upload" hinzu
$  git status                      # Der Status ist nun grün > Dateien sind Upload-bereit (Optional) 
$  git commit -m "Mein Kommentar"  # Upload wird "commited" > Kommentar zu Dokumentationszwecken ist dafür notwendig
$  git status                      # Dateien werden nun als "zum Pushen bereit" angezeigt
$  git push                        #Upload bzw. Push wird durchgeführt
```
## VirtualBox
VirtualBox ist eine von zahlreichen Virtualisierungsanwendungen. Man kann es ganz einfach von der Herstellerseite herunterladen und installieren. Anschliessend kann man ganz leicht eine Virtuelle Maschine mittels ISO Dateien erstellen.
![](C:\Users\flori\M300\M300-Services\10-Toolumgebung\VirtualBox.png "VirtualBox")
## thema
