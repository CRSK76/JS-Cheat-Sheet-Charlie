Allgemeines
===========

-> node.js ist die JS-Engine -> übersetzt JS für das Betriebssystem und den Browser, so dass JS auf dem Server und im Browser nur noch ausgeführt wird.

-> im Terminal *-> **node -v** = gibt die aktuelle Version von node.js aus*, die auf dem Rechner installiert ist

-> *__node__ ruft node.js im Terminal auf -> __node + dateiname.js__*

Nodemon
-------

-> wird über npm Packedmanager installiert. *__npm list -g__  zeigt an, welche Packete von npm global installiert sind*

-> **npm install -g nodemon** installiert Nodemon global auf dem Rechner

-> mit **npm init** initialisert dann Nodemon in einem bestimmten Projektordner für ein bestimmtes Projekt, so dass die **packed.json** und die **nodemon.json** angelegt werden. Mit einem **src-ordner**, in dem die zu überwachenden Dateien hineinkommen

-> **npm run** zeigt im Allgemeinen, welche Befehle es gibt

### Quelltext packed.json

    {
        "name": "Projektname des jeweiligen Projektes",
        "version": "1.0.0",
        "description": "",
        "main": "Name der main.js, falls eine vorhanden ist",
        "type": "module",
        "scripts": {
            "test": "echo \"Error: no test specified\" && exit 1",
            "watchjs": "nodemon"
     },
        "keywords": [],
        "author": "Charlie",
        "license": "ISC",
        "devDependencies": {
        "nodemon": "^2.0.21"
     }
    }

-> bei scripts muss **"watchjs": "nodemon"** stehen oder **"watchjs": "nodemon dateiname"** (der zu überwachenden Datei, falls es sich nur um eine Datei handelt, die zu überwachen ist)

### mit src-Ordner und Watching

#### Quelltext der nodemon.json

    {
        "watch": [
             "src/"
        ],
        "exec": "node src/main.js"
    }

-> es muss die main.js angegeben werden, und der Source-Ordner-Pfad, wo die zu überwachenden Dateien dann abgespeichert werden

#### Quelltext der main.js

    import './datei.js';
    import './datei.js';

-> hier werden die zu überwachenden Dateien importiert

**-> WICHTIG!! Die Importfunktion wird bald nicht mehr unterstützt.**

-> Die Arbeit mit nodemon kann wichtig sein für größere JS-Projekte.

### Starten von Nodemon mit watchjs

-> **npm run watchjs** startet das Watching, muss aber in dem Ordner gestartet werden, in dem auch die konfigurierte packed.json liegt

-> **strg c** stoppt den Nodemon-Server

