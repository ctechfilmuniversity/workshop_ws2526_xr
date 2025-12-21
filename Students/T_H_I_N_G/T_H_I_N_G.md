**Disclaimer**

Aktueller Stand: Die **Android-/Quest-APK baut noch nicht**, weil ein von mir erstellter **Custom-DSP** (Faust → FMOD) zu Build-Fehlern führt. Die **Desktop-Builds laufen jedoch stabil** und zeigen die geplante Funktionalität. (Deshalb auch die Verspätung)

Hier ist die APK ohne Audio:
https://mega.nz/folder/uaJ0BZDY#dWpFvbkViPdaYhzKawY-pQ

---

## Projektüberblick

Das Projekt ist eine VR-Installation im Inneren eines ausserirdischen Raumschiffs. Im Zentrum steht ein farbiges, verspieltes, biomechanisches Instrument, das lose an H. R. Giger angelehnt ist, aber in einer pastelligen, fast hyperpopartigen Farbwelt umgesetzt wird. Durch Interaktionen mit verschiedenen Teilen des Alien-Körpers erzeugen Besucher Klänge, steuern einen Sequencer und “entschlüsseln” so spielerisch eine Art Alien-Botschaft.

---

## Interaktion & Klang

* **16-Step-Sequencer:**
  16 Sphären im Raum repräsentieren Steps. Wenn man mit der Hand durch eine Sphäre fährt, wird der Step ein- oder ausgeschaltet, die Farbe ändert sich, und die aktuell gespielte Stufe wird über Emission hervorgehoben.
  Die Sequencer-Logik läuft zeitbasiert in Unity, mit frei veränderbarem **BPM**.

* **BPM-Rad:**
  Ein physisches Rad im Raum steuert das Tempo. Das BPM-Signal wird in Unity ausgewertet und beeinflusst direkt die Sequencer-Geschwindigkeit.

* **SkrillexAlienGrowl:**
  Steckt man die Hand in den Mund des Aliens, wird ein eigens gestalteter **Skrillex-ähnlicher Growl-Sound** über FMOD ausgelöst (Custom DSP + Effekte).

* **Drums / Oneshots:**
  Über zusätzliche “Drum-Pads” können One-Shot-Samples gespielt werden, deren Lautstärke von der Intensität der Bewegung abhängt (velocity-sensitiv).

* **Audio-Pipeline:**
  Unity verwaltet Sequencer-Timing und Interaktionen, FMOD übernimmt Sounddesign, Effekte und perspektivisch binaurale Räumlichkeit. Ein erster **Faust-basierter DSP** ist integriert (funktioniert bereits im Desktop-Build, verursacht aber noch Probleme im Android-Build).

---

## Technisches Setup

* **Engine:** Unity 6 LTS, VR-Template mit XR Origin (Hands)
* **Zielplattform:** Primär Meta Quest 3 (APK aktuell in Arbeit), Desktop-Version lauffähig
* **Audio:** FMOD Studio + Custom DSP (Faust)
* **Versionierung:** Git/GitHub mit sauber konfiguriertem `.gitignore` und Git LFS für Unity- und FMOD-Assets

---

## Team & Rollen

* **Lynn** – 3D-Modelling der Alien-Strukturen und der Umgebung
* **Johannes** – VR-Interaktion (XR-Rig, Hand-Colliders, Trigger-Logik, BPM-Rad)
* **Aydin** – Audio-Konzept und Implementierung (Sequencer-System, FMOD-Integration, Custom DSP, SkrillexAlienGrowl, Drums), plus **Unterstützung im 3D-Modelling** des zentralen Instruments
