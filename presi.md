layout: true
class: content

---


class: center, middle, whiteFont
background-image: url(img/gears.jpg)

# ProcessEngineJS
Demo einer verteilen Typescript Process Engine
???
- Projekt vorstellen
- stellt euch szenario vor
- Kunde meldet sich

---


class: next_slow
background-image: url(img/office.jpg)
???
- hat Autovermietung

--


class: next_slow
.float_left.margin_sm[&zwnj;]
&zwnj;
***
.speech[![:img_width 90px](img/car_rent.png)]
???
- will reservierungs-prozess automatisieren
- bestellen läuft manuell
- sachbearbeiter -> email, eintragen, antworten
- Kunde weiß was er von der Software will


---


class: next_slow, blackFont
background-image: url(img/office.jpg)

.float_left.margin_sm[Was soll umgesetzt werden?]
&zwnj;
***
.speech[.center[![:img_width 90px](img/car_rent.png).padding_left_sm[![:img_width 90px](img/process.svg)]]
- **Prozessablauf**
- Bestellung aufgeben
- ggf. genehmigen
- Reservierung speichern
- Bestätigung senden (email)
- Schlüssel bereitstellen]

???
- client: prozessablauf & erwartungen
- unsere Aufgabe: technische Umsetzung -> in code gießen -> Programm erstellen

---


class: next_slow, blackFont
background-image: url(img/office.jpg)

.center[
.float_left.margin_sm[Was soll umgesetzt werden?]
.float_right.margin_sm[Wie soll es umgesetzt werden?]]

&zwnj;

***
.speech[.center[![:img_width 90px](img/car_rent.png).padding_left_sm[![:img_width 90px](img/process.svg)]]
- **Prozessablauf**
- Bestellung aufgeben
- ggf. genehmigen
- Reservierung speichern
- Bestätigung senden (email)
- Schlüssel bereitstellen]
.speech_own[.center[![:img_width 90px](img/toolbox.svg)]
- **implementierung**
- Tech Stack
- Infrastruktur
- Services]

???
- Fachliche (was) vs technische (wie) sicht auf gleiche software
- herkömmlich: Programm beinhaltete fachliche und technische implementierung (verschmolzen)
- alternativ: ProcessEngine bauen


---


class: next_slow, blackFont
background-image: url(img/office.jpg)

.center[
.float_left.margin_sm[Was soll umgesetzt werden?]
.float_right.margin_sm[Wie soll es umgesetzt werden?]]


&zwnj;
***
.speech[.center[![:img_width 90px](img/car_rent.png).padding_left_sm[![:img_width 90px](img/process.svg)]]
- **Prozessablauf**
- Bestellung aufgeben
- ggf. genehmigen
- Reservierung speichern
- Bestätigung senden (email)
- Schlüssel bereitstellen]
<img class="pe_chain" src="img/chain.svg" style="left: 19px"/>
<div class="center_box" style=" display: inline-block;width: 348px; margin-top: 40px;">
  <div class="center_box_content box_white" style="width: 250px;">
ProcessEngineJS
<hr>
![:img_width 90px](img/gears.svg)
  </div>
</div>
<img class="pe_chain" src="img/chain.svg" style="left: -19px"/>
.speech_own[.center[![:img_width 90px](img/toolbox.svg)]
- **implementierung**
- Tech Stack
- Infrastruktur
- Services]

???
- Lose kopplung, bringt beide sichten zusammen

- Definition Process Engine
  - führt Modell aus (Orchestriert)
  - herkömmlich: einzelne Serveranwendung

- Definition PEJS
  - Framework, stellt Toolset bereit, um eigene PE zu bauen, die aus beliebig vielen teilnehmern/clients auf verschiedensten geräten besteht
  - (verteilt), einzeln oder mehrere führen prozess aus, je nach features/rechten/verfügbarkeit

- ProcessEngine-Implementierung sieht wie folgt aus:

---


class: next_slow
background-image: url(img/office.jpg)
background-size: 200%

<img class="pe_chain_big" src="img/chain.svg" style="left: -6%"/>
<img class="pe_chain_big" src="img/chain.svg" style="right: -6%"/>

<div class="center_box">
  <div class="center_box_content box_white big_box">

.center.margin_bottom_sm[### ProcessEngineJS]

???
- Prozess ausführen benötigt zwei dinge


--


.left_half[
Auszuführender Prozess  
(BPMN)
***
![:img_width 300px](img/process_2_bw.svg)]

???
- einen Prozess
  - einfacher Beispielprozess
  - muss Implementierung für Prozesskomponenten her

--


.right_half[
.center[Implementierung der Prozesskomponenten
(JavaScript)]
.left.code_block[
```Typescript
import {
  createTransport,
  SentMessageInfo,
  SendMailOptions} from 'nodemailer';
import {IMailService} from 'mail_service_contracts';

export class MailService implements IMailService {

  public config: any;

  public send(mailOptions: SendMailOptions): Promise<SentMessageInfo> {
    const transporter = createTransport(this.config.transporter);
    return transporter.sendMail(mail);
  }
}
```
]
]

  </div>
</div>
???
- Wenn prozesskomponenten-implementierungen vorhanden: muss ausgeführt werden
- Prozess und implementierung müssen zusammengebracht werden
- hier kommt PEJS ins spiel


---


class: next_slow
background-image: url(img/office.jpg)
background-size: 200%

<img class="pe_chain_big" src="img/chain.svg" style="left: -6%"/>
<img class="pe_chain_big" src="img/chain.svg" style="right: -6%"/>

<div class="center_box">
  <div class="center_box_content box_white big_box">

.center.margin_bottom_sm[### ProcessEngineJS]

.left_half[
Auszuführender Prozess  
(BPMN)
***
![:img_width 300px](img/process_2_bw.svg)]


.right_half[
.center[Implementierung der Prozesskomponenten
(JavaScript)]
.left.code_block[
```Typescript
import {
  createTransport,
  SentMessageInfo,
  SendMailOptions} from 'nodemailer';
import {IMailService} from 'mail_service_contracts';

export class MailService implements IMailService {

  public config: any;

  public send(mailOptions: SendMailOptions): Promise<SentMessageInfo> {
    const transporter = createTransport(this.config.transporter);
    return transporter.sendMail(mail);
  }
}
```
]

<div class="entity_box box_blue">
  <div class="left_half">
.left.entity_title[Eigene Services/Entitäten]
.entity[MailService]
.entity[MailReportEntity]
  </div>
  <div class="right_half">
.left.entity_title[ProcessEngine Services/Entitäten]
.entity[ServiceTask]
.entity[NodeInstance]
.entity[StartEvent]
.entity[EndEvent]
.entity[weitere...]
  </div>
</div>
<div class="entity_box box_orange">
.left.entity_title[ProcessEngine Basis]
.entity[process_engine]
.entity[core]
.entity[messagebus]
.entity[feature]
.entity[routing]
.entity[bootstrapper]
.entity[datastore]
.entity[iam]
.entity[addict_ioc]
</div>
]

  </div>
</div>

???
- viele kleine komponenten
- blau = weitere Services
- orange = basis/kern von PEJS
- blau + orange = gesamte anwendung / deployable client
- Wenn process_engine den task ausführt, und bei "Mail Senden" ankommt

---


class: next_slow
background-image: url(img/office.jpg)
background-size: 200%

<img class="pe_chain_big" src="img/chain.svg" style="left: -6%"/>
<img class="pe_chain_big" src="img/chain.svg" style="right: -6%"/>

<div class="center_box">
  <div class="center_box_content box_white big_box">

.center.margin_bottom_sm[### ProcessEngineJS]

.left_half[
Auszuführender Prozess  
(BPMN)
***
![:img_width 300px](img/process_2.svg)]


.right_half[
.center[Implementierung der Prozesskomponenten 
(JavaScript)]

.left.code_block.glow[
```Typescript
import {
  createTransport,
  SentMessageInfo,
  SendMailOptions} from 'nodemailer';
import {IMailService} from 'mail_service_contracts';

export class MailService implements IMailService {

  public config: any;

  public send(mailOptions: SendMailOptions): Promise<SentMessageInfo> {
    const transporter = createTransport(this.config.transporter);
    return transporter.sendMail(mail);
  }
}
```
]


<div class="entity_box box_blue">
  <div class="left_half">
.left.entity_title[Eigene Services/Entitäten]
.entity.glow[MailService]
.entity[MailReportEntity]
  </div>
  <div class="right_half">
.left.entity_title[ProcessEngine Services/Entitäten]
.entity.glow[ServiceTask]
.entity.glow[NodeInstance]
.entity[StartEvent]
.entity[EndEvent]
.entity[weitere...]
  </div>
</div>
<div class="entity_box box_orange">
.left.entity_title[ProcessEngine Basis]
.entity.glow[process_engine]
.entity[core]
.entity[messagebus]
.entity[feature]
.entity[routing]
.entity[bootstrapper]
.entity[datastore]
.entity[iam]
.entity[addict_ioc]
</div>
]

  </div>
</div>
???
- processengine -> NodeInstance (nicht pfeil oder gate) -> ServiceTask -> MailService
- irgendwo deployen
- kann mail senden
- So viel zum aufbau einer ProcessEngineJS-Anwendung
- TODO: Analogie finden


---


class: next_slow, blackFont
background-image: url(img/office.jpg)

.center[
.float_left.margin_sm[Was soll umgesetzt werden?]
.float_right.margin_sm[Wie soll es umgesetzt werden?]]


&zwnj;
.speech[.center[![:img_width 90px](img/car_rent.png).padding_left_sm[![:img_width 90px](img/process.svg)]]
- **Prozessablauf**
- Bestellung aufgeben
- ggf. genehmigen
- Reservierung speichern
- Bestätigung senden (email)
- Schlüssel bereitstellen]
<img class="pe_chain" src="img/chain.svg" style="left: 19px"/>
<div class="center_box" style=" display: inline-block;width: 348px; margin-top: 40px;">
  <div class="center_box_content box_white" style="width: 250px;">
ProcessEngineJS
<hr>
![:img_width 90px](img/gears.svg)
  </div>
</div>
<img class="pe_chain" src="img/chain.svg" style="left: -19px"/>
.speech_own[.center[![:img_width 90px](img/toolbox.svg)]
- **implementierung**
- Tech Stack
- Infrastruktur
- Services]

???
- Anwendung mit PEJS fertig bauen
- Kunde glücklich
- alternative: Direkt implementieren
  - Programm bauen, dass kundenprozesse direkt implementiert


---


class: next_slow, blackFont
background-image: url(img/office.jpg)

.center[
.float_left.margin_sm[Was soll umgesetzt werden?]
.float_right.margin_sm[Wie soll es umgesetzt werden?]]


&zwnj;
.speech[.center[![:img_width 90px](img/car_rent.png).padding_left_sm[![:img_width 90px](img/process.svg)]]
- **Prozessablauf**
- Bestellung aufgeben
- ggf. genehmigen
- Reservierung speichern
- Bestätigung senden (email)
- Schlüssel bereitstellen]
<div class="center_box" style=" display: inline-block;width: 537px; margin-top: 40px;">
  <div class="center_box_content box_white" style="width: 336px; max-width: none; height: 230px">
Alternative: Direkt implementieren
    <div class="appbg" style="top: 175px; left: 528px"></div>
    <div class="processbg" style="position: absolute; top: 175px; left: 528px"></div>
  </div>
</div>
.speech_own[.center[![:img_width 90px](img/toolbox.svg)]
- **implementierung**
- Tech Stack
- Infrastruktur
- Services]
???
- Warum ProcessEngine-Overhead aufbringen?


---

class: next_slow, blackFont
background-image: url(img/chart_background_2.jpg)
# .center[Warum den ProcessEngine-Overhead aufbringen?]
???
- zusammengefasst: Trennung von fachlicher und technischer Implementierung
- Programm betrachten, ohne code zu sehen


--


class: next_slow
<div class="overhead_part">
.center[#### Das Programm betrachten]
<img src="img/see.jpg", style="width: 100%; border-radius: 2px"/>
<hr>
.center[ohne den Code zu sehen]
</div>
???
- Programm verstehen, ohne Quelltext zu durchsuchen


--


class: next_slow
<div class="overhead_part">
.center[#### Das Programm verstehen]
<img src="img/grasp.jpg", style="width: 100%; border-radius: 2px"/>
<hr>
.center[ohne Quelltext zu durchsuchen]
</div>
???
- Programmablauf anpassen, ohne Code anzufassen


--


class: next_slow
<div class="overhead_part">
.center[#### Den Ablauf anpassen]
<img src="img/edit.jpg", style="width: 100%; border-radius: 2px"/>
<hr>
.center[ohne den Code anzufassen]
</div>
???
- Fachliche Implementierung gestützt, statt vergraben
- Modell = Doku und Bestandteil, auch für nicht-nerds


--


class: next_slow
***
***
***
#### .center[Die Fachliche Implementierung wird durch Software gestützt, statt in ihr vergraben]
#### .center[Das Modell ist Doku und Bestandteil zugleich, und kann auch mit nicht-nerds besprochen werden]

???
TODO: Besseres "Verstehen"-Foto finden (close-up?)


---


class: center, middle, next_slow, blackFont
background-image: url(img/chart_background_2.jpg)
# .center[Demo-Zeit!]
???
TODO: Demo vorbereiten


---


class: left, next_slow, blackFont
background-image: url(img/chart_background_2.jpg)
.left_half[
# Mögliche Szenarien
]


--


***
- Szenario 1
???
TODO: einzelne szenarion auflisten


--


- Szenario 2


--


- Szenario 3


--


- Szenario 4


---

class: left, next_slow, blackFont
background-image: url(img/chart_background_2.jpg)
# .left_half[Ausblick]

--


***
- Isomorphie
???
TODO: einzelne ausblick-punkte auflisten


--


- Offlinefähigkeit


--


- Verteilte Ausführung


--


- Ausblick 4


--

***
# .center[Vielen Dank fürs zuhören!]


--


***
# .center[... Fragen?]

