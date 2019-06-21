# Coding Academy


## Agenda - Coding-Session JAVA/TDD

* Tag 1:
     * 14:30 - 15:00 - Intro
     * 15:00 - 18:00 - Coding Session Part 1
* Tag 2:
     * 9:00 - 12:00 - Coding Session Part 2
     * Mittagspause
     * 13:00 - 14:30 - Coding Session Part 2
     * 14:30 - 15:00 - Wrap-Up
     * 15:00 - 15:30 - Vorbereitung der Präsentation
     * 15:30 - 16:00 - Präsentation der Lösungen (2 Leute)

## Tag 1
### Intro

- Begrüßung von Fred / Alex
- Ziel von der heutigen der heutigen Session:
   - nicht nur JAVA, sondern Best-Practices in der SW-Entwicklung
   - *Programmieren können viele, aber Software entwickeln nur wenige!*
- Technologien / Prinzipien:
   - JAVA - https://www.tiobe.com/tiobe-index/
   - OO-Programming https://medium.freecodecamp.org/object-oriented-programming-concepts-21bb035f7260
   - Rivescript (general) https://www.rivescript.com/
   - SpringBoot - http://spring.io/projects/spring-boot
   - Hamcrest - http://hamcrest.org/JavaHamcrest/
   - Maven - https://maven.apache.org/
   - GIT https://git-scm.com/
   - Docker https://docs.docker.com/get-started/
   - Test-Driven-Development (TDD) http://agiledata.org/essays/tdd.html
   - Pair-Programming https://en.wikipedia.org/wiki/Pair_programming



### PART 1
- Programmieren des ChatBot mit TDD
   * Diskussion während des Programmierens gewünscht!
   * 'git commit' nicht vergessen
   * Neues Maven Project anlegen
      * GrouppId = de.coding.academy / artifactId = chatbot
      * Wähle ein beliebigesVerzeichnis für 'Project location'
   * Lege einer neue Klasse 'ChatBot' an (nur der Skeleton)
   * Anlegen eines GIT Repository:
      * Erzeuge GIT repo mit Kommando 'git init' inkl. Datei .gitignore
      * Dann commit mit Kommando 'git add . && git commit'
   * TDD - Zuerst den Test! Den ersten Test schreiben wir zusammen
      * harmcrest zu pom.xml hinzufügen - https://mvnrepository.com/artifact/org.hamcrest/hamcrest-all/1.3 to pom.xml (siehe coding-handout)
      * neue Test-Klasse 'ChatBotTest'
         * Hierfür in der Klasse Chatbot Ctrl+N drücken und Test auswählen. Bitte JUnit 4 wählen und Test-Klasse anlegen.
         * Eine neue Method testSayHelloBot() anlegen:
             * Zuerst erzeugen wir ein Instanz der Klasse Chatbot in der Test-Klasse ChatBotTest
             * Dann nutzen wir die Instanz der Klasse Chatbot, um auf die (künftige) Methode 'getReply()' aufzurufen
             * Da diese Methode in 'Chatbot' noch nicht exisitert, müssen wir sie anlegen
             * Anschließend nutzen wir Hamcrest, um auf das erwartete Ergebnis von 'getReply()' zu asserten
             * Achtung: Für den Fall, dass der Test mit dem Fehler "Error:java: error: release version 5 not supported" abbricht, dann bitte in den Project Settings auf JAVA Version 8 umstellen
         * Der Test sollte fehlschlagen! Somit haben wir den ersten Schritt im TDD Zyklus erfolgreich absolviert.
   * Eigenständiges Schreiben von weiteren 2-3 Tests
      * danach kurze Diskussion über die Tests
      * nach finalisieren der Tests - git commit
   * Logik der ChatBot-Klasse programmiren (geführt von Fred/Alex)
      * Fred/Alex zeigen Rivescript-Playground https://play.rivescript.com/ zur Demo
      * Maven-Dependency hinzufügen https://mvnrepository.com/artifact/com.rivescript/rivescript-core/0.10.0
      * dann 'rivescript' Folder anlegen create (gleiches Level wie 'src' folder) + rivescript file anlegen
      * *Run the tests until they pass successfully!*
      * MainClass anlegen, welche die ChatBot-Klasse aufruft
         * ChatBot-Klasse wird instanziert
         * Lesen der Eingabe von der Konsole in while-loop
         * Test mit start der MainClass aus der IDE und chatten
   * optional: Fred/Alex anderes Bsp. mit "swear-word case" in Rivescript
   * Ziel: In der IDE-Konsole kann man mit dem ChatBot chatten!

## Tag 2
### PART 2
- Programmieren eines RESTful-Web-Service für den ChatBot via SpringBoot
  * Um den Bot via HTTP anzusprechen, implementieren wir nun einen REST/HTTP-Server mit dem SpringBoot-Framework
  * Maven-Deps für SpringBoot (siehe coding-handout)
  * neues Package 'rest' anlegen
     * eigentlich auch hier zuerst den Test schreiben mit MockMVC!
        * aus Zeitgründen überspringen wir das
     * neue Klasse ChatBotApp als @SpringBootApplication anlegen
  * Fred/Alex zeigen wie zu implementieren sind
     * neue Klasse GetHelloController mit @GetMapping("/") für einfache Hallo-Response des Webservice
     * git add / git commit
     * neue Klasse PostMsgController mit @PostMapping("/") für Kommunikation mit ChatbOt
     * git add / git commit
- Verpacken des RESTful Webservice in Docker-Image:
  * Dockerfile anlegen, Build image and run image
  * Test des REST-Service via Postman (sollte installiert sein)

### Wrap-Up
- Was haben wir heute gelernt?
  - Automatisierung - "Automate everything!"
  - Wiederverwendung - "Don't reinvent the wheel!"
  - Qualität und Code-Struktur durch TDD
  - Docker für DevOps
  - GIT für Versionierung und Sharing Code

### Vorbereitung Präsentation
Pro Team sind 10 Minuten Ergebnispräsentation vorgesehen.

Eigentverantwortliches ausarbeiten der Präsentation:
- Wer präsentiert?
- Was wird präsentiert?
- Wie wird präsentiert?

