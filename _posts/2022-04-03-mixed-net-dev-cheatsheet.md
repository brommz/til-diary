---
layout: post
title: "Mixed .NET DEV cheatsheet"
date: 2022-04-03 12:00:00 +0100
description: ""
img:  # Add image post (optional)
---

```bash

# Windows symbolic link (mklink link_name dest_el)
mklink /d "C:\Program Files (x86)\Microsoft Visual Studio\2017\BuildTools" "C:\Program Files (x86)\Microsoft Visual Studio\2017\Professional" 
# IIS Starting Web Services
Set-Service 'WAS' -StartupType Manual
Set-Service 'W3SVC' -StartupType Manual
Start-Service 'WAS'
Start-Service 'W3SVC'

dotnet nuget locals all -c # clear all nuget caches


# REDIS
npm install -g redis-cli
rdcli -h host_name -p 6379
https://redis.io/commands # commands
FLUSHALL 
KEYS *
INFO

# DOTNET
dotnet new console
dotnet test --filter="Name~SomeTests" --no-restore -c Release
dotnet test --filter="ClassName=Namespace.SomeTests" --no-restore -c Release

# POSTGRES JSON
* The operator -> returns JSON object field by key 
    SELECT info -> 'customer' AS customer -- -> tutaj dostaniemy jako json rezultat
    FROM orders;
* The operator ->> returns JSON object field by text 
    SELECT info ->> 'customer' AS customer -- -> tutaj dostaniemy jako text rezultat
    FROM orders;
* chaining
    SELECT info -> 'items' ->> 'product' as product
    FROM orders
    ORDER BY product;
* WHERE
    SELECT info ->> 'customer' AS customer
    FROM orders
    WHERE info -> 'items' ->> 'product' = 'Diaper';
* json_object_keys  -> pobiera jako kolumny z json klucze
    SELECT json_object_keys (info->'items')
    FROM orders;
* INNE OPERATOR https://devhints.io/postgresql-json

```


# SHOTCUTS

## ---VSC---
* F8 - Go to next error or warning
* Ctrl+Shift+O -> szuka symbole w pliku np. metody czy komdendy
* Ctrl+Shift+\ -> jump to enclosing bracket nawias


## ---VS - moje wypracowane skróty ---
* (lub ctrl + shift + ) Alt+Up/Down               Move code up or down () - skacze po kodzie (metody, zmienne)
* Ctrl + ]                  For matching braces and parentheses.
* Ctrl+Up, Ctrl+Down        Przesuwają ekran, a kursor na stałe
* Ctrl+R, Ctrl+R            Refaktoring nazwyt
* Shift+Del	                Usuwa całą linię (z kopiowaniem)	
* Ctrl+Shift+L	            Usuwa linię (bez kopiowania)
* Ctrl+L	                  Wycina linię

* ALT + 16 itd...	►    16    pogrubiona strzałka w prawo i inne Unicode znaki
* Win+E	                    Open Windows Explorer
* Ctrl + Alt + D            Open TODOs
* Windows+Arrows            Przenoszenie okienka w Windows

* Ctrl+U Ctrl+R -> Uruchomienie testów z pliku
* Ctrl+U Ctrl+D -> Uruchomienie testów z pliku (DEBUG)
* Ctrl+Alt+T -> Unit Tests Session (REsharper)

* Shift + Alt + L -> (moje) Lokalizacja pliku w Solution Explorer

* Shift + Alt + PgDown/PgUp -> przeskakiwanie między Errorami

* Ctrl + K + K -> tworzenie zakładek

* Ctrl + Shift + V -> schowek Visual Studio :)

* Shift + F12 -> znajdowanie wszystkich użyć (trochę jak referencji) np. get/set, zmiennej itd.
* Ctrl + Shift + Alt + B -> Go to implementation
* Ctrl + Fn + Home/End -> skakanie koniec/początek dokumentu

## Snippets
* Ctrl + E + L      Resharperowe Live Template (takie snippety)

* Alt + Insert -> pomocniczne typu zrób Dispose, ToString, czy inne Templates

# Skróty systemowe
* Windows + V -> Schowek
* 
