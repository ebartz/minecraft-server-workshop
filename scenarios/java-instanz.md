# Intro

In diesem Schritt wirst du nun eine Java Minecraft Instanzen in Crafty aufsetzen.

<br></br>

![Java Bedrock](https://frogblog.grootmoor.de/wp-content/uploads/2022/01/minecraft-java-vs-bedrock-1.jpg)

## Minecraft Java Edition:

### Plattformen und Betriebssysteme:
   - Verfügbar nur auf PCs.
   - Unterstützt Windows, macOS und Linux.

### Spielmechanik und Features:
   - Bietet einige exklusive Features, die in der Bedrock Edition nicht verfügbar sind, wie bestimmte Redstone-Mechanismen und Modding-Fähigkeiten.
   - Hat eine umfangreiche Modding-Community, die eine Vielzahl von Mods und benutzerdefinierten Inhalten ermöglicht.

### Multiplayer und Server:
   - Bietet die Möglichkeit, dedizierte Server zu erstellen und zu hosten, was eine größere Kontrolle über die Servereinstellungen und -modifikationen ermöglicht.
   - Multiplayer ist hauptsächlich PC-zentriert, mit einer Spielergemeinschaft, die oft älter und technisch versierter ist.

### Updates und Entwicklung:
   - Wird separat von der Bedrock Edition aktualisiert, wobei einige Updates zeitgleich veröffentlicht werden, während andere exklusive Inhalte haben.
   - Tendiert dazu, neue Features zuerst zu erhalten, bevor sie in die Bedrock Edition integriert werden.

<br></br>

Zusammenfassend lässt sich sagen, dass die Java Edition ideal für PC-Spieler ist, die an einer tiefgreifenden Modding-Erfahrung und detaillierten Serverkontrollen interessiert sind. Beide Editionen erhalten regelmäßige Updates und haben ihre eigenen einzigartigen Merkmale, die sie für verschiedene Spielergruppen attraktiv machen.


# Java Instanz

Um deine erste Instanz zu erstellen musst du dich zunächst in deinem [Crafty Controller](https://${vminfo:minecraft:public_ip}:8443) anmelden.

<p></p>


Vermutlich meckert dein Browser in dem Moment darüber, dass du gerade keine sichere Website aufrufst. Das liegt daran, dass wir gerade per HTTPS auf den Server zugreifen aber kein valides Zertifikat hinterlegt ist.

<br></br>
Deine Crafty Instanz erreichst du unter: **[https://${vminfo:minecraft:public_ip}:8443](https://${vminfo:minecraft:public_ip}:8443)**
<br></br>

Um das zu umgehen klicke in deinem Browser auf `Erweitert` und dann auf `Weiter zu ${vminfo:minecraft:public_ip} (unsicher)`

![SSL Error](https://kinsta.com/de/wp-content/uploads/sites/5/2018/08/your-connection-not-private-error-chrome-1.png)


Die Zugangsdaten findest du hier:

```ctr:minecraft
cat /var/opt/minecraft/crafty/crafty-4/app/config/default-creds.txt
```

<br></br>

Danach gehts dann unter `Servers` mit `+ Create New Server` weiter:

![Create New Server](https://github.com/ebartz/minecraft-server-workshop/blob/main/images/create-server.png?raw=true)

### Grundeinstellungen

Nun sind die Servereinstellungen zu setzen. Für den ersten Java Server sollte dann alles so aussehen:

![Java Settings](https://github.com/ebartz/minecraft-server-workshop/blob/main/images/create-java.PNG?raw=true)

Nutze dazu bitte folgende Einstellungen:
<p></p>

`Server Type`: **Vanilla** <p></p>

`Server Select`: **vanilla** <p></p>

`Server Version`: **1.20.4** <p></p>

`Server Name`: **Mein Server** <p></p>

`Minimum Memory`: **1** <p></p>

`Maximum Memory`: **2** <p></p>

`Server Port`: **25565** <p></p>

<br></br>

Anschließend bestätige dieses Formular bitte mit `Build Server!`.
<p></p>
Bevor dein Minecraft Server gestartet werden kann, läd Crafty zunächst noch die benötigen Daten herunter. Darunter befinden sich neben den richtigen Java Datein auch die Grundeinstellungen ohne die ein Server nicht starten kann.

`Warte daher bis der Build Prozess fertig ist!`

### Server Starten

Wenn du auf der linken Seite im Crafty Menü auf `Dashboard` klickst, kommst du zur Übersicht über alle Server.

<br></br>
Dort kannst du nun deinen ersten Server starten in dem du auf den `Play button` klickst.

![Java Start](https://github.com/ebartz/minecraft-server-workshop/blob/main/images/start-server.PNG?raw=true)

Das erste Starten des Server kann mehrere Minuten dauern. Das hängt von der Leistung deines Servers ab. Schließlich muss die Welt für deinen Server erst noch gebaut werden. Das kennst du vielleicht auch wenn du in Minecraft eine neue Welt erstellst.

Außerdem musst du meistens noch die Bedingungen von Minecraft beim ersten Starten des Servers bestätigen.

![Java Start](https://github.com/ebartz/minecraft-server-workshop/blob/main/images/java-accept-eula.PNG?raw=true)

### Das Terminal

Wenn du schauen willst, wie es deinem Server geht, wähle diesen zunächst im Menü entweder unter `Dashboard` oder unter `Servers` aus. Danach sollte sich dann diese Ansicht öffnen:

![Java Terminal](https://github.com/ebartz/minecraft-server-workshop/blob/main/images/java-server-terminal.PNG?raw=true)

Hier kannst du auch Server Befehle ausführen oder schauen was dein Server so macht oder wer diesem zuletzt beigetreten ist.

### Weitere Einstellungen

Wenn du im Bereich Files schaust, siehst du dort alle Dateien deines Servers. Eine der wichtigsten ist dabei die `server.properties.`

![Java Files](https://github.com/ebartz/minecraft-server-workshop/blob/main/images/java-files-properties.PNG?raw=true)

Die Einstellungen in dieser Datei werden allerdings erst nach einem neustart des Servers übernommen. Du kannst deinen Server jederzeit über das `Terminal Menü` über den Button `Restart` neu starten. Alle Spieler die währenddessen mit dem Server verbinden waren verlieren dabei allerdings die Verbindung zum Server. Daher ist es immer nett deinen mitspielenden Bescheid zu geben.


# Zusammenfassung

Wenn du den Schritten wie beschrieben befolgt hast sollten nun eine Java Minecraft Instanzen lhaben.

<br></br>

Hier sind die Verbindungsdaten noch einmal zusammengefasst:

`Java`: ${vminfo:minecraft:public_ip}:25565

<br></br>

Wenn du die Minecraft Java Edition auf einem deiner Geräte installiert hast, kannst du gern ausprobieren ob dein Server funktioniert.

<br></br>

![Minecraft Java Cover](https://cdn.cdkeys.com/700x700/media/catalog/product/n/e/new_project_83_.jpg)
