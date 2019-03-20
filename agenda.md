# Coding Academy


## Agenda - Coding-Session JAVA

* 9:30 - 13:00 - Coding Session Part 1
* 13:00 - 14:00 - Mittagspause
* 14:00 - 16:00 - Coding Session Part 2
* 16:15 - 17:00 - Präsentation der Lösungen (JAVA, JavaScript, Python)


### Intro (9:30 Uhr - max. 10:15)

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
   
   
- Gruppen von 2 Personen zum programmieren ('Pair Programming')


### PART 1 (10:15 - 13 Uhr)
- Programmieren des ChatBot mit TDD
   * Diskussion während des Programmierens gewünscht!
   * 'git commit' nicht vergessen
   * Neues Maven Project anlegen
      * GrouppId = de.example.codingacademy / artifactId = chatbot
   * Create de.example.codingacademy.ChatBot Class (nur der Skeleton)
   * git init/commit f. pom.xml and + ChtaBot class
   * Den ersten Test schreiben wir zusammen
      * harmcrest zu pom.xml hinzufügen - https://mvnrepository.com/artifact/org.hamcrest/hamcrest-all/1.3 to pom.xml (siehe coding-handout)
      * neue Test-Klasse de.example.codingacademy.ChatBotTest anlegen
         * method sayHelloBot() anlegen, welche die Methode getReply() testet
   * Nun schreiben die Gruppen mind. 2 Tests eigenständig
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

 
- Mittag 13-14:00 Uhr

### PART 2 (14:00 - 15:45 Uhr)
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
 
### Wrap-Up (15:45 - 16:00 Uhr)
- Was haben wir heute gelernt?
  - Automatisierung - "Automate everything!"  
  - Wiederverwendung - "Don't reinvent the wheel!"
  - Qualität und Code-Struktur durch TDD
  - Docker für DevOps
  - GIT für Versionierung und Sharing Code
  
