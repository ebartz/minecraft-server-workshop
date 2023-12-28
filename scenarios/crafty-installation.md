# Intro

Es gibt viele Möglichkeiten Minecraft Server zu verwalten.

Eine davon ist der [Crafty Controller](https://craftycontrol.com/). Crafty ist kostenlos und steht als [OpenSource](https://de.wikipedia.org/wiki/Open_Source#:~:text=Als%20Open%20Source%20(aus%20englisch,Lizenzbedingungen%20meistens%20kostenfrei%20genutzt%20werden.) Software zur Verfügung.

<br></br>

Crafty bietet dabei eine Benutzeroberfläche an, die über den Browser gesteuert werden kann. Das macht die Steuerung und Konfiguration deiner Minecraft Server einfacher.

<br></br>

In diesem Abschnitt werden wir deshalb den Crafty Controller Installieren und uns mit der Steuerung vertraut machen.

<br></br>

![Minecraft Server Admin](https://chaos-craft.io/image.png)

# Installation
Als erstes müssen wir den Quellcode von Crafty herunterladen. Dies passiert mit [Git](https://git-scm.com/). Git ist ein Programm was dabei hilft Quellcode zu versionieren. Außerdem hilft es auch wenn mehrere Menschen auf den Quellcode zugreifen wollen.

<p></p>

```ctr:minecraft
git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git
```

Nachdem wir den Quellcode heruntergeladen haben können wir ein Script nutzen, welches von Crafty bereitgestellt wird.

```ctr:minecraft
cd crafty-installer-4.0 && ./install_crafty.sh
```

Das Installationsscript möchte nun allerhand Dinge von uns wissen um die Installation vornehmen zu können.<p></p>


### Abhängigkeiten Installieren
Das Installationsskirt erkennt als ersten das Betriebssystem und schägt vor die Abhängigkeiten zu installieren.

```
[+] Info:- Linux Check Success
[+] Info:- Python Version Check - 3.10
We detected your os is: ubuntu - Version: 22.04

Install ubuntu_22_04.sh requirements? - ['y', 'n']:
```

Die Frage ist einfach mit `y` zu bestätigen.

```ctr:minecraft:1
y
```

### Installationspfad
Das Script installiert Crafty normalerweise im Verzeichnis `/var/opt/minecraft/crafty`.

```
[+] Info:- Crafty's Default install directory is set to: /var/opt/minecraft/crafty

Install Crafty to this directory? /var/opt/minecraft/crafty - ['y', 'n']:
```


Dies wollen wir auch bei unserer Installation so machen und bestätigen daher erneut mit `y`.

```ctr:minecraft:1
y
```

Das Script stellt meistens einen Fehler fest. Denn die Berechtigungen für den Crafty Ordner sind noch nicht korrekt. Es schlägt daher vor die Berechtigungen zu korrigieren:

```
[-] Warning: Unable to write to /var/opt/minecraft/crafty - Permission denied

Do you want us to fix this permission issue? - ['y', 'n']:
```

Auch dieses mal bestätigen wir wieder mit `y`.

```ctr:minecraft:1
y
```

### Die richtige Version auswählen
Das Script fragt nun welche Crafty Version wir nehmen wollen. Empfohlen ist es die aktuelle Stabile Version zu verweden. Um dies zu tun muss die nächste Frage mit `master` beantwortet werden.

```ctr:minecraft:1
master
```

### Erstellung der Service Datei
Im Linux Betriebssystem gibt es meisten Steuerdateien die für Services zuständig sind die im Hintergrund laufen.

<p></p>

Crafty soll am besten automatisch gestaret werden und vom Betriebssystem verwaltet werden.

```
[+] Info:- Making start and update scripts for you

Would you like to make a service file for Crafty? - ['y', 'n']:
```

Daher ist auch diese Frage mit `y` zu beantworten.

```ctr:minecraft:1
y
```

Wenn alles erfolgreich gelaufen ist sollte die Ausgabe nun so aussehen:

```
[+] Info:- Cleaning up temp dir
[+] Info:- Congrats! Crafty is now installed!
[+] Info:- We created a user called 'crafty' for you to run crafty as. (DO NOT RUN CRAFTY WITH ROOT OR SUDO) Switch to crafty user with 'sudo su crafty -'
[+] Info:- Your install is located here: /var/opt/minecraft/crafty
[+] Info:- You can run crafty by running /var/opt/minecraft/crafty/run_crafty.sh
[+] Info:- You can update crafty by running /var/opt/minecraft/crafty/update_crafty.sh
[+] Info:- A service unit file has been saved in /etc/systemd/system/crafty.service
[+] Info:- run this command to enable crafty as a service- 'sudo systemctl enable crafty.service'
[+] Info:- run this command to start the crafty service- 'sudo systemctl start crafty.service'
```
# Crafty starten

Wir haben nun Crafty erfolgreich installiert. Damit wir es auch nutzen können, muss der Dienst aber noch gestartet werden.
<p></p>
Darüber hinaus wäre es sinnvoll, dass Crafty auch automatisch startet, wenn unser Server mal neugestartet wird.

<br></br>

In Ubuntu 22.04 können Dienste mit dem Tool `systemctl` gesteuert werden.

Um dafür zu sorgen, dass Crafty automatisch gestartet wird müssen wir folgendes ausführen:

```ctr:minecraft
systemctl enable crafty
```


Nun müssen wir Crafty noch starten:

```ctr:minecraft
systemctl start crafty
```


Wenn wir uns nun den Status des Dienstes anzeigen lassen wollen, dann können wir das mit dem Befehl machen:

```ctr:minecraft
systemctl status crafty
```


Wenn alles richtig installiert wurde, sollte die Ausgabe so aussehen:

```
● crafty.service - Crafty 4
     Loaded: loaded (/etc/systemd/system/crafty.service; enabled; vendor preset: enabled)
     Active: active (running) since Tue 2023-12-26 13:32:17 UTC; 5s ago
   Main PID: 4640 (bash)
      Tasks: 10 (limit: 9237)
     Memory: 44.3M
        CPU: 1.518s
     CGroup: /system.slice/crafty.service
             ├─4640 /usr/bin/bash /var/opt/minecraft/crafty/run_crafty_service.sh
             └─4641 python3 main.py -d

Dec 26 13:32:18 dynamic-4uck65gapc-2cf6eb34 bash[4641]: [+] Crafty: 12/26/2023 01:32:18 PM - INFO:        Generating a k>
Dec 26 13:32:18 dynamic-4uck65gapc-2cf6eb34 bash[4641]: [+] Crafty: 12/26/2023 01:32:18 PM - INFO:        Setting up Cra>
Dec 26 13:32:19 dynamic-4uck65gapc-2cf6eb34 bash[4641]: [+] Crafty: 12/26/2023 01:32:19 PM - INFO:        https://91.107>
Dec 26 13:32:19 dynamic-4uck65gapc-2cf6eb34 bash[4641]: [+] Crafty: 12/26/2023 01:32:19 PM - INFO:        Server Init Co>
Dec 26 13:32:20 dynamic-4uck65gapc-2cf6eb34 bash[4641]: [+] Crafty: 12/26/2023 01:32:20 PM - INFO:        Stats collecti>
Dec 26 13:32:21 dynamic-4uck65gapc-2cf6eb34 bash[4641]: [+] Crafty: 12/26/2023 01:32:21 PM - INFO:        Launching Sche>
Dec 26 13:32:21 dynamic-4uck65gapc-2cf6eb34 bash[4641]: [+] Crafty: 12/26/2023 01:32:21 PM - INFO:        Launching comm>
Dec 26 13:32:21 dynamic-4uck65gapc-2cf6eb34 bash[4641]: [+] Crafty: 12/26/2023 01:32:21 PM - INFO:        Launching log >
Dec 26 13:32:21 dynamic-4uck65gapc-2cf6eb34 bash[4641]: [+] Crafty: 12/26/2023 01:32:21 PM - INFO:        Launching real>
Dec 26 13:32:22 dynamic-4uck65gapc-2cf6eb34 bash[4641]: [+] Crafty: 12/26/2023 01:32:22 PM - INFO:        Checking Inter>
lines 1-21/21 (END)
```

# Zusammenfassung

**Glückwunsch**! du hast erfolgreich den Crafty Controller installiert.

<p></p>

Wenn du mehr über Crafty heruasfinden möchtest, kannst du in der [Dokumentation](https://docs.craftycontrol.com/pages/user-guide/user-role-config/) viele weitere Informationen finden.


![Minecraft Success](https://media-cldnry.s-nbcnews.com/image/upload/t_fit-760w,f_auto,q_auto:best/streams/2012/May/120511/364650-minecraft.jpg)
