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

### Quelltext packed.json

    {
        "name": "variables-operators-strings",
        "version": "1.0.0",
        "description": "",
        "main": "",
        "type": "module",
        "scripts": {
            "test": "echo \"Error: no test specified\" && exit 1",
            "watchjs": "nodemon"
     },
        "keywords": [],
        "author": "Carsten",
        "license": "ISC",
        "devDependencies": {
        "nodemon": "^2.0.21"
     }
    }

-> bei scripts muss **"watchjs": "nodemon"** stehen oder **"watchjs": "nodemon dateiname"** (der zu überwachenden Datei, falls es sich nur um eine Datei handelt, die zu überwachen ist)


