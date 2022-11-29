---
sidebar_position: 1
---

# Flashfig

Wie konfiguriere ich viele Router auf ein mal?

## Vorraussetzungen

- eine valide Konfigurations Datei (.rsc) 
- einen Windows Rechner, auf welchem [Flashfig](https://download.mikrotik.com/routeros/7.6/flashfig.exe) heruntergeladen wurde.
- pysikalisch Zugang zum Router.


## Einrichten des Windows (Flashfig) Servers

Die heruntergeladene .exe Datei ausführen
- Die **Boot Client Address** setzten. Diese Adresse muss nur im selben Netzwerk wie der Router liegen.
- Dann die Konfigurationsdatei auswählen:
  - Also über die Schaltfäche **Browse** zur Konfigurationsdatei navigieren, diese auswählen und schließlich öffnen.
  - Dann die Datei aus der **scripts** Liste auswählen und auf **Select** drücken.

## Einrichten des Routers

Wenn man ein RouterBOARD Device benutzt, sollte folgene Einstellung bereits eingestellt worden sein.
Bei anderen Routern meldet man sich per WinBox am Router an und führt im Terminal folgenden Command aus
```bash
system/routerboard/settings/set boot-device=flash-boot
```
oder
```bash
system/routerboard/settings/set boot-device=flash-boot-once-then-nand
```

## Flashen eines Routers
- Den Router vom Netz nehmen (Abschalten)
- Den Laptop / Computer / ... auf den Eth 1, (Internet) Port anstecken
- Den Flashfig server mit der Schaltfäche **Activate** starten
- Jetzt den Router einschalten
- Jetzt in Flashfig auf eine neue Nachricht mit dem Inhalt *Flashfigged* unter **Messages** warten, wenn dann der Router beginnt zu blinken, dann kann man diesen vom Strom entfernen und sich den nächsten vorknüpfen. 