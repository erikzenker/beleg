# Analyse von Ansätzen zur Beschleunigung von SAT-Lösern durch dedizierte Hardware-Komponenten
* [Latex sources](beleg.tex) of my "grosser beleg" from august 2011
* [Precompiled pdf](beleg.pdf)

## Introduction

In der Informatik beschäftigt man sich mit einer Vielzahl von kombinatori-
schen Problemen und wie diese effizient gelöst werden können. Nicht jedes
Problem ist gleich schwer bzw. leicht zu lösen, weshalb sie in sogenannte
Problemklassen eingeteilt werden. Eine Klasse ist die Klasse der nichtdeter-
ministisch polynomiell vollständigen Probleme. Für NP-vollständige Pro-
bleme gibt es bisher keine Möglichkeit, diese effizient zu lösen. Ein Durch-
probieren von allen Lösungsmöglichkeiten würde sehr viel Zeit in Anspruch
nehmen und wird deshalb nur bei kleiner Problemgröße durchgeführt. Des-
halb werden oft problemspezifische Heuristiken benutzt, wodurch trotz ex-
ponentieller Komplexität durchaus gute Ergebnisse erzielt werden können.
Auch das Erfüllbarkeitsproblem (engl. Satisfiability Testing SAT) gehört zur
Klasse der NP-vollständigen Probleme. Moderne SAT Solver können SAT-
Probleme mit mehreren millionen Variablen und Klauseln lösen und werden
beständig weiter entwickelt.

Die Rechnerarchitekturen auf denen SAT-Solver ausgeführt werden ändern
sich unaufhaltsam in Richtung Many-Core-Architekturen. Bereits heutige
Serversysteme haben 12 unabhängige Rechenkerne [1] auf einem Prozes-
sorchip, und selbst einfache Desktopsysteme sind standardmäßig mit 2 bis
4 Kernen ausgestattet.

Ein Nachteil von SAT-Solvern ist bisher, dass ihr Algorithmus auf sequentiel-
le Verarbeitung optimiert ist, obwohl bereits mehrere parallele Einheiten zur
Verfügung stehen. Deshalb müssen die Algorithmen angepasst werden, um
auch in Zukunft die vorhandenen Ressourcen effektiv ausnutzen zu können.
Man kann noch einen Schritt weiter gehen. Statt der Auslagerung der Algo-
rithmen auf einige wenige Kerne, nutzt man die hohe Parallelität von Field
Programmable Gate Arrays (FPGAs). Ein Ansatz ist es den Inferenzmecha-
nismus, welcher ca. 80 bis 90% der Rechenleistung in aktuellen SAT-Solver
belegt, auf einen FPGA auszulagern und ihn hochparallel auszuführen.
