Dies ist das Repository für die Webseite http://www.larp-hamburg.de

Diese Webseite wird mit dem statischen Jekyll Generator generiert.


# Installieren

https://jekyllrb.com/docs/installation/ubuntu/


# Starten des lokalen Webservers

Um die Webseite anzuzeigen, muss ein folgende Befehl eingegeben im Verzeichnis ~/git/larp-hamburg werden:

Dazu öffnet man ein Terminal   (Windows Taste und dann Terminal schreiben)

cd ~/git/larp-hamburg
bundle exec jekyll serve

Dann läuft die Webseite unter dieser URL

http://127.0.0.1:4000/

# Konfigurieren

Wir nutzen das populäre minimal mistakes theme, dieses kann konfiguriert werden.
Die Optionen sind hier beschrieben.

https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/

Image gallery wird hier beschrieben.

https://jekyllcodex.org/without-plugin/image-gallery/

# Auf den live Server aufspielen

Eine neue Version der Webseite wird automatisch gebaut sobald ein neuer Commit auf den `main` gepusht wird.
Dies geschieht durch die GitHub action in `.github/workflows/build.yml`.

Zum Publizieren einer neuen Version muss ein build unter https://bertrax.vogella.com/job/larp-hamburg/ gestartet werden.
Hiezu unter der genannten URL auf den Button `Build with Parameters` drücken.
Wenn man auf das live System publizieren möchte dann, einfach auf `Build` drücken, ohne das `Remote Server` Parameter zu ändern.

Der Job https://bertrax.vogella.com/job/larp-hamburg/ wird über das `Jenkinsfile` auf dem `build` Branch definiert.
