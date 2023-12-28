# Intro

In diesem Schritt wirst du nun deine Bedrock Minecraft Instanzen in Crafty aufsetzen.

<br></br>

![Java Bedrock](https://frogblog.grootmoor.de/wp-content/uploads/2022/01/minecraft-java-vs-bedrock-1.jpg)

## Minecraft Bedrock Edition:

### Plattformen und Betriebssysteme:
   - Eine plattformübergreifende Edition, verfügbar auf Windows, iOS, Android, Xbox, PlayStation und Nintendo Switch.
   - Ermöglicht plattformübergreifendes Spielen, sodass Spieler auf verschiedenen Geräten zusammen spielen können.

### Spielmechanik und Features:
   - Hat einige einzigartige Features und Gameplay-Aspekte, die in der Java Edition nicht verfügbar sind, wie bestimmte Blöcke und Gegenstände.
   - Weniger modding-fähig im Vergleich zur Java Edition, bietet jedoch offizielle Add-Ons und den Marketplace für benutzerdefinierte Inhalte.

### Multiplayer und Server:
   - Ermöglicht leichteren Zugriff auf Multiplayer-Spiele und offizielle Server, mit integrierten Freundenlisten und Einladungssystemen.
   - Bietet Realms, die einfach zu bedienende, private, von Mojang gehostete Server sind.

### Updates und Entwicklung:
   - Erhält Updates oft zur gleichen Zeit wie die Java Edition, jedoch mit einigen Unterschieden in den Features und der Implementierung.
   - Zielt darauf ab, ein einheitliches Spielerlebnis über alle unterstützten Plattformen hinweg zu bieten.

<br></br>

Zusammenfassend lässt sich sagen, dass die Bedrock Edition sich an eine breitere Zielgruppe richtet und plattformübergreifendes Spielen sowie eine vereinfachte Handhabung ermöglicht.

# Bedrock Instanz

### Server Import vorbereiten
Es kann bei unterschiedlichen Internetanbietern dazu kommen, dass die Bedrock Edition nicht heruntergeladen werden kann. Das ist leider auch beim Anbieter der Testumgebung der Fall. Daher müssen wir noch eine Datei herunterladen um danach eine Server Instanz importieren zu können.

<p></p>

Das pissiert mit diesem Befehl:

```ctr:minecraft
wget -O /tmp/bedrock.zip https://chaos-craft.io/bedrock-base.zip
chmod 755 /tmp/bedrock.zip
```

### Mit Crafty verbinden

Um deine erste Instanz zu erstellen musst du dich in deinem [Crafty Controller](https://${vminfo:minecraft:public_ip}:8443) anmelden.

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

### Server erstellen

Danach gehts dann unter `Servers` mit `+ Create New Server` weiter:

![Create New Server](https://github.com/ebartz/minecraft-server-workshop/blob/main/images/create-server.png?raw=true)

### Grundeinstellungen

Wähle bitte als erstes dass du einen Bedrock Server erstellen möchtest:

![Create Bedrock](https://github.com/ebartz/minecraft-server-workshop/blob/main/images/create-bedrock.PNG?raw=true)

Nun sind die Servereinstellungen zu setzen. Achte bitte darauf, dass in diesem Schritt ein Server importiert werden soll. Für den Bedrock Server sollte dann alles so aussehen:

![Bedrock Settings](https://github.com/ebartz/minecraft-server-workshop/blob/main/images/bedrock-import.PNG?raw=true)

Nutze dazu bitte folgende Einstellungen:
<p></p>

`Server Name`: **Bedrock Server** <p></p>

`Server Executable File`: **bedrock_server** <p></p>

`Server Port`: **19132** <p></p>


Bevor du diesen Schritt abschließen kannst, muss noch ein Ordner in unserer Zip Datei ausgewählt werden:

![Bedrock Select Files](https://github.com/ebartz/minecraft-server-workshop/blob/main/images/bedrock-select-files.PNG?raw=true)


<br></br>

Anschließend bestätige dieses Formular bitte mit `Import Server!`.
<p></p>
Bevor dein Minecraft Server gestartet werden kann, läd Crafty zunächst noch die benötigen Daten herunter.

`Warte daher bis der Import Prozess fertig ist!`

### Server Starten

Wenn du auf der linken Seite im Crafty Menü auf `Dashboard` klickst, kommst du zur Übersicht über alle Server.

<br></br>
Dort kannst du nun deinen ersten Server starten in dem du auf den `Play button` klickst.

![Java Start](https://github.com/ebartz/minecraft-server-workshop/blob/main/images/bedrock-start.PNG?raw=true)

Das erste Starten des Server kann mehrere Minuten dauern. Das hängt von der Leistung deines Servers ab. Schließlich muss die Welt für deinen Server erst noch gebaut werden. Das kennst du vielleicht auch wenn du in Minecraft eine neue Welt erstellst.

### Das Terminal

Wenn du schauen willst, wie es deinem Server geht, wähle diesen zunächst im Menü entweder unter `Dashboard` oder unter `Servers` aus. Danach sollte sich dann diese Ansicht öffnen:

![Bedrock Terminal](https://github.com/ebartz/minecraft-server-workshop/blob/main/images/bedrock-terminal.PNG?raw=true)

Hier kannst du auch Server Befehle ausführen oder schauen was dein Server so macht oder wer diesem zuletzt beigetreten ist.

### Weitere Einstellungen

Wenn du im Bereich Files schaust, siehst du dort alle Dateien deines Servers. Eine der wichtigsten ist dabei die `server.properties.`

![Bedrock Files](https://github.com/ebartz/minecraft-server-workshop/blob/main/images/bedrock-properties.PNG?raw=true)

Die Einstellungen in dieser Datei werden allerdings erst nach einem neustart des Servers übernommen. Du kannst deinen Server jederzeit über das `Terminal Menü` über den Button `Restart` neu starten. Alle Spieler die währenddessen mit dem Server verbinden waren verlieren dabei allerdings die Verbindung zum Server. Daher ist es immer nett deinen mitspielenden Bescheid zu geben.

# Zusammenfassung

Wenn du den Schritten wie beschrieben befolgt hast solltest du nun eine Bedrock Minecraft Instanzen haben.

<br></br>

Hier sind die Verbindungsdaten noch einmal zusammengefasst:

<p></p>

`Bedrock`: ${vminfo:minecraft:public_ip}:19132

<br></br>

Wenn du die Minecraft Bedrock Edition auf einem deiner Geräte installiert hast, kannst du gern ausprobieren ob dein Server funktioniert.

<br></br>

![Minecraft Bedrock Cover](https://www.gamemovieportal.ch/games/Minecraft/covers/Minecraft-Game-Movie-Portal.jpg_pbcr.jpg)
