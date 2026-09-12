# Artefakt Stimmgerät – APK-Build-Anleitung

Laut Capacitor benötigt ein Android-Build die Android-Entwicklungsumgebung mit Android Studio, Android SDK und nativen Build-Werkzeugen; die Projektbasis allein erzeugt noch keine APK. [web:72][web:60]

## Enthalten

- Chromatische Tuner-App im deutschen Notensystem.
- Grundstimmung C, D, Es, F, G, As, B in dunkel-edlem Grün.
- Außentöne wie Cis, E, Fis, A und H in dunklem Grau.
- App-Icon als stilisierte Harfe in SVG.
- Web-Datei als Basis für Capacitor oder WebView-Projekt. [file:1][file:2]

## APK lokal bauen

1. Node.js installieren.
2. Android Studio samt SDK installieren, wie von Capacitor für Android vorgegeben. [web:72]
3. Ein Capacitor-Projekt anlegen oder das vorhandene Projekt verwenden und die Webdatei unter `www/index.html` einfügen. [web:49]
4. Android-Plattform hinzufügen: `npx cap add android`. [web:49]
5. Danach in das Android-Projekt wechseln und per Gradle bauen; in Community-Beispielen wird dafür `./gradlew assembleRelease` genutzt, anschließend Signierung und Alignment für die fertige APK. [web:64]
6. Für eine Testversion ohne Release-Signierung ist meist auch `./gradlew assembleDebug` möglich. [web:60]

## Icon einbauen

Die stilisierte Harfe liegt als SVG vor und kann als Master-Asset für Android-Launcher-Icons genutzt werden. Für Android werden daraus typischerweise verschiedene Rastergrößen für `mipmap-*` erzeugt. [web:68]

## Hinweis

In dieser Umgebung konnte keine APK kompiliert werden, weil die erforderliche Java-/Android-Toolchain nicht vorhanden ist. Capacitor setzt für das native Android-Build diese Werkzeuge voraus. [web:72][web:60]
