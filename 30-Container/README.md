#### Inhaltsverzeichnis

- [Docker](#docker)
    - [Dockerfile](#dockerfile)
- [Vergleich Vorwissen](#vergleich-vorwissen)
- [Reflexion](#reflexion)

# Docker
Ich habe nun einiges über das VM erstellen mit Vagrant gelernt. Nun gibt es aber noch andere Möglichkeiten Services laufen zu lassen. Dafür haben wir uns Docker angeschaut. Mit Docker kann man ganz leicht verschiedenste Container erstellen und gleichzeitig laufen lassen. Folgende Befehle sind sehr hilfreich im Umgang mit Docker:

**docker run** <br>
* Ist der Befehl zum Starten neuer Container.
* Der bei weitem komplexesten Befehl, er unterstützt eine lange Liste möglicher Argumente.
* Ermöglicht es dem Anwender, zu konfigurieren, wie das Image laufen soll, Dockerfile-Einstellungen zu überschreiben, Verbindungen zu konfigurieren und Berechtigungen und Ressourcen für den Container zu setzen.

Standard-Test:
```Shell
    $ docker run hello-world
```

Startet einen Container mit einer interaktiven Shell (interactive, tty):
```Shell
    $ docker run -it ubuntu /bin/bash
```

Startet einen Container, der im Hintergrund (detach) läuft:
```Shell
    $ docker run -d ubuntu sleep 20
```

Startet einen Container im Hintergrund und löscht (remove) diesen nach Beendigung des Jobs:
```Shell
    $ docker run -d --rm ubuntu sleep 20
```

Startet einen Container im Hintergrund und legt eine Datei an:
```Shell
    $ docker run -d ubuntu touch /tmp/lock
```

Startet einen Container im Hintergrund und gibt das ROOT-Verzeichnis (/) nach STDOUT aus:
```Shell
    $ docker run -d ubuntu ls -l
```

**docker ps** <br>
* Gibt einen Überblick über die aktuellen Container, wie z.B. Namen, IDs und Status.

Aktive Container anzeigen:
```Shell
    $ docker ps
```

Aktive und beendete Container anzeigen (all):
```Shell
    $ docker ps -a
```

Nur IDs ausgeben (all, quit):
```Shell
    $ docker ps -a -q
```

**docker images** <br>
* Gibt eine Liste lokaler Images aus, wobei Informationen zu Repository-Namen, Tag-Namen und Grösse enthalten sind.

Lokale Images ausgeben:
```Shell
    $ docker images
```

Alternativ auch mit `... image ls`:
```Shell
    $ docker image ls
```

![](../Images/Docker01.png "Docker")

**docker rm und docker rmi** <br>
* `docker rm`
    *  Entfernt einen oder mehrere Container. Gibt die Namen oder IDs erfolgreich gelöschter Container zurück.
* `docker rmi`
    *  Löscht das oder die angegebenen Images. Diese werden durch ihre ID oder Repository- und Tag-Namen spezifiziert.

Docker Container löschen:
```Shell
    $ docker rm [name]
```

Alle beendeten Container löschen:
```Shell
    $ docker rm `docker ps -a -q`
```

Alle Container, auch aktive, löschen:
```Shell
    $ docker rm -f `docker ps -a -q`
```

Docker Image löschen:
```Shell
    $ docker rmi ubuntu
```

Zwischenimages löschen (haben keinen Namen):
```Shell
    $ docker rmi `docker images -q -f dangling=true`
```

**docker start** <br>
* Startet einen (oder mehrere) gestoppte Container. 
    * Kann genutzt werden, um einen Container neu zu starten, der beendet wurde, oder um einen Container zu starten, der mit `docker create` erzeugt, aber nie gestartet wurde.

Docker Container neu starten, die Daten bleiben erhalten:
```Shell
    $ docker start [id]
```

**Container stoppen, killen** <br>
* `docker stop`
    * Stoppt einen oder mehrere Container (ohne sie zu entfernen). Nach dem Aufruf von `docker stop` für einen Container wird er in den Status »exited« überführt.
* `docker kill`
    * Schickt ein Signal an den Hauptprozess (PID 1) in einem Container. Standardmässig wird SIGKILL gesendet, womit der Container sofort stoppt.

**Informationen zu Containern** <br>
* `docker logs`
    * Gibt die "Logs" für einen Container aus. Dabei handelt es sich einfach um alles, was innerhalb des Containers nach STDERR oder STDOUT geschrieben wurde.
* `docker inspect`
    * Gibt umfangreiche Informationen zu Containern oder Images aus. Dazu gehören die meisten Konfigurationsoptionen und Netzwerkeinstellungen sowie Volumes-Mappings.
* `docker diff`
    * Gibt die Änderungen am Dateisystem des Containers verglichen mit dem Image aus, aus dem er gestartet wurde.
* `docker top`
    * Gibt Informationen zu den laufenden Prozessen in einem angegebenen Container aus.

### Dockerfile
***
Man kann mit Docker, wie bei Vagrant, ein File erstellen und bearbeiten. Dies geht wie folgt:
```Shell
    $ docker build -t mysql .
```

Starten:
```Shell
    $ docker run --rm -d --name mysql mysql
```

Funktionsfähigkeit überprüfen:
```Shell
    $ docker exec -it mysql bash
```

Überprüfung im Container:
```Shell
    $ ps -ef
    $ netstat -tulpen
```
![](../Images/Dockerfile.png "Dockerfile")




# Vergleich Vorwissen
Ich habe davor schon mal was von Docker gehört gehabt, aber habe es selbst noch nie benutzt. Ich habe nun durch das Modul die wichtigsten Befehle und Anwendungsbereiche von Docker kennengelernt und denke, dass ich auch in Zukunft noch einiges damit machen werde.
# Reflexion
Da ich die Abgabe der LB02 sehr herausgezögert habe, habe ich erst viel zu spät mit der LB03 angefangen und als ich entlich mich darum kümmern wollte, war ich auch noch krank. Was bedeutet, dass ich aus eigenverschulden, nicht sehr viel machen konnte und deswegen auch meine Note in dem Modul nicht gut sein wird. Aber ich habe daraus gelernt und werde in Zukunft mich wieder darum bemühen, meine Arbeiten in den nächsten Modulen besser zu machen.

[⇧ **Nach oben**](#inhaltsverzeichnis)