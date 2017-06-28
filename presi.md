layout: true
class: content
background-image: url(img/office_2_bright.jpg)


---


class: center, middle, whiteFont
background-image: url(img/gears.jpg)

# ProcessEngineJS
Demo einer verteilten TypeScript Process Engine
???
- Ich will ein kleines Rollenspiel mit euch machen
- Unser unternehmen, die PottJS GmbH
- Konnte vor 3 Monaten einen super Auftrag an Land ziehen


---

.left_half.center[
![:img_width 50%](img/client.svg)
]
.right_half[
.speech[
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.   

Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi. Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.   

Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.   

Nam liber tempor cum soluta nobis eleifend option congue nihil imperdiet doming id quod mazim placerat facer possim assum. Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.   

Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis.
]]
???
- Kunde hat uns in langen meetings seine Anforderungen dargelegt
- Wir direkt: Jo, machen wir


---

.left_half[
.speech_own[
### IoC
### Clean code
### Microservices
### Single-Responsibility
### Schichtenarchitektur
### Test-driven development
### Continuous Deployment
]]
.right_half.center[
![:img_width 50%](img/developer.svg)
]
???
- Nach allen Regeln der Kunst


---


class: middle
.left_half.center[
![:img_width 50%](img/client_unhappy_2.svg)
]
.right_half.center[
![:img_width 100%](img/shiny_app.svg)
]
???
- Seht euch den kunden an: unzufrieden bei shiny app
- Er sagt: nicht wie beschrieben
- Wo im code ist anforderung umgesetzt?


---


class: middle
.left_half[
.left_half[![:img_width 90%](img/client_unhappy_2.svg)]
.right_half[.speech[
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.   

Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.
]]
]
.right_half.left[
![:img_width 57%](img/bad_placement.svg)
]
???
- anforderungen <-> Projektstruktur
- Wie kommt es zu unstimmigkeiten?


---


class: top
.center[![:img_width 10%](img/conflict.svg)]
.left_half.center[
.left_half[
![:img_width 90%](img/client_unhappy_2.svg)
]
.right_half[
.speech[
![:img_width 100%](img/documents.svg)
]
]
]
.right_half.center[
.right_half[
![:img_width 90%](img/developer.svg)
]
.left_half[
.speech_own[
![:img_width 100%](img/toolbox_bright.svg)
]
]
]
???
- unterschiedliche sprachen
- Fachlich (fließtext) <-> technisch (code)


---


class: top
.center[![:img_width 10%](img/no_conflict.svg)]
.left_half.center[
.left_half[
![:img_width 90%](img/client.svg)
]
.right_half[
.speech[
![:img_width 100%](img/process_bright.svg)
]
]
]
.right_half.center[
.right_half[
![:img_width 90%](img/developer_happy.svg)
]
.left_half[
.speech_own[
![:img_width 100%](img/process_bright.svg)
]
]
]
.center[# BPMN]
.center[### Business Process Model and Notation]
???
- Die gleiche Sprache sprechen (BPMN)
- Realisiert durch Process Engine


- gemeinsam Prozesse entwickeln
- Kunden haben bereits dutzende Prozessdiagramme


- einfacher Prozess kann so aussehen


---

class: middle
background-image: none
![:img_width 100%](img/process_2.svg)
???
- Einzelne Prozesselemente erklären
- Prozesse werden auch etwas größer


---


background-image: url(img/create_claim.svg)
background-size: contain
???
- Brauerei-Retourenprozess
- Ist echter Prozess der tatsächlich in verwendung ist
***
- Kunde versteht den Prozess
- Den **will man nicht in Code** vergraben haben
***
- Modelle existierten schon vor Software


---


class: center, blackFont
background-image: url(img/chart_background_2.jpg)
background-size: cover
# .center[Warum lohnt es sich, so zu arbeiten?]
<div class="overhead_part">
.center[#### Das Programm betrachten]
.center[ohne den Code zu sehen]
<hr>
<img src="img/see.jpg", style="width: 50%; border-radius: 2px"/>
</div>


---


class: center, blackFont
background-image: url(img/chart_background_2.jpg)
background-size: cover
# .center[Warum lohnt es sich, so zu arbeiten?]
<div class="overhead_part">
.center[#### Das Programm verstehen]
.center[ohne Quelltext zu durchsuchen]
<hr>
<img src="img/grasp.jpg", style="width: 50%; border-radius: 2px"/>
</div>


---



class: center, blackFont
background-image: url(img/reservation_bright_2.png)
background-size: contain
# .center[Warum lohnt es sich, so zu arbeiten?]

<hr class="margin_bottom_lg"/>
<hr class="margin_bottom_lg"/>
#### .center[Die fachliche Implementierung ist nicht im Code vergraben!]
<hr class="margin_bottom_lg"/>
#### .center[Das Modell ist Doku und Programmbestandteil zugleich!]
???
- fachliche Implementierung nicht im Code vergraben
***
- "Überlegt mal, Das Modell ist **Doku** UND **Bestandteil** zugleich
  
  -> kann auch mit nicht-nerds besproche werden"


---


background-image: url(img/reservation.png)
background-size: contain
???
- DEMO TIME!
***
- Setup beschreiben
  - Fzg.-klasse *&&* extras wählen

  - Luxusklasse genehmigen
  
  - Preisermittlung *&&* bestätigung

  - Speichern *&&* Mail senden

  - Schlüsselkasten öffnen



---


class: middle, blackFont
background-image: url(img/collaborate_bright.jpg)
## Die ProcessEngineJS
Ein in TypeScript entwickeltes Framework zum Erstellen eigener, verteilter Process Engines!
- Typescript
- Node/Browser
- IoC
- Microservices
- Schichtenarchitektur
???
- ProcessEngineJS


---


class: middle, blackFont
background-image: url(img/collaborate_bright.jpg)
## Die ProcessEngineJS
Vorteile gegenüber anderen Process Engines:
- basiert auf JavaScript
- Erstellen eigener Services und Entities
- Anbinden externer Services und Schnittstellen
- Deployen auf verschiedenen Plattformen
- verteilte Ausführung
- selbst entwickelt -> für die eigenen Bedürfnisse angepasst
???
- ProcessEngineJS


---


class: center, middle, blackFont
background-image: url(img/collaborate_bright.jpg)
## Eine ProcessEngine verbindet die Vorteile beider Welten
eine direkte Einbindung der fachlichen Prozesse

basierend auf der technischen Umsetzung eines modernen Stacks
???
- Code kann in sauberem Stack geschrieben werden, und der Prozess direkt integriert werden


---


class: center, middle, blackFont
background-image: url(img/collaborate_bright.jpg)
# Vielen Dank an

.left_half.center[
## QUANTUSflow Software GmbH
]

.right_half.center[
## Huf Secure Mobile GmbH
]
