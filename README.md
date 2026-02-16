# Raport: Wykorzystanie asystentów AI w procesie projektowym

## 1. Skład zespołu projektowego
* **Ivan Berezka**
* **Mikita Tsarkovich**
* **Daniil Yakaulev**

## 2. Wstęp i charakterystyka współpracy z AI
Podczas realizacji projektu „Nowoczesny Samolot Pasażerski”, nasz zespół aktywnie zintegrował proces modelowania 3D z zaawansowanymi narzędziami sztucznej inteligencji – **Gemini** oraz **ChatGPT**. Wykorzystanie AI nie ograniczało się jedynie do prostych zapytań, lecz stanowiło fundament naszej strategii rozwiązywania problemów (troubleshooting) i optymalizacji pracy.

Sztuczna inteligencja pełniła rolę wirtualnego mentora i konsultanta technicznego, co przyniosło następujące korzyści:
* **Skrócenie krzywej uczenia się:** Zamiast tracić czas na wielogodzinne przeszukiwanie dokumentacji Blendera, otrzymywaliśmy precyzyjne instrukcje dotyczące konkretnych narzędzi (np. Knife Project czy Parenting).
* **Zarządzanie topologią:** AI pomogło nam utrzymać czystą siatkę (mesh) w stylu low-poly, co jest kluczowe dla wydajności modeli 3D.
* **Wsparcie wizualne i edukacyjne:** Modele AI selekcjonowały dla nas najlepsze materiały źródłowe na YouTube, co pozwoliło na naukę dobrych praktyk bezpośrednio od profesjonalistów.
* **Efektywność zespołowa:** Dzięki AI szybko ustaliliśmy workflow integracji plików (Parent-Child), co zapobiegło błędom przy łączeniu naszych niezależnie tworzonych komponentów.

## 3. Wykorzystanie AI do generowania i analizy referencji
Praca nad modelem 3D wymaga precyzyjnych rzutów (blueprintów). Wykorzystaliśmy **ChatGPT** do analizy kluczowych cech aerodynamicznych oraz wygenerowania spójnego zestawu referencji wizualnych. Pozwoliło to naszemu zespołowi pracować na jednym, uniwersalnym wzorcu nowoczesnego odrzutowca, zapewniając spójność proporcji między kadłubem, skrzydłami a silnikami.

Poniżej przedstawiamy dokumentację z procesu konsultacji dotyczących referencji oraz wygenerowane materiały:

![Czat z AI o referencjach 1](5231372271245530319.jpg)
![Czat z AI o referencjach 2](5231372271245530320.png)

---

## 4. Skonsolidowane logi z konsultacji technicznych

### Sekcja Ivana Berezki (Konsultacje z Gemini):
**Ivan:** Cześć! Razem z kolegami robimy model 3D samolotu. Moja kolej na detale. Muszę dodać okna i drzwi. Próbowałem użyć Booleana, ale na okrągłym fuzelażu wszystko się gnie i cieniowanie wygląda fatalnie. Jak to ugryźć?

**Gemini:** Cześć! Boolean przy zaokrąglonych powierzchniach to najkrótsza droga do błędów. Użyj funkcji **Knife Project**. Narysuj obrys okna jako osobny obiekt (Plane) i rzutuj na model w widoku ortograficznym.

**Ivan:** Próbowałem, ale nie reaguje. Masz filmik, który pokazuje to krok po kroku?

**Gemini:** Kolejność zaznaczania jest kluczowa. Zobacz: [Blender Knife Project tool quick guide]. Najpierw zaznacz „nóż”, potem z Shiftem kadłub, wchodzisz w Edit Mode i dopiero wybierasz Mesh > Knife Project. Pamiętaj o widoku z boku (Numpad 3)!

**Ivan:** Załapało! Ale samolot jest pusty w środku. Muszę modelować fotele?

**Gemini:** Absolutnie nie. Zrób okna metodą „Black Glass”. Przypisz wyciętym kształtom osobny, czarny materiał z niskim Roughness (0.1). Ukryje to wnętrze i nada profesjonalny wygląd przy minimalnym nakładzie pracy.

**Ivan:** Przy Shade Smooth silnik wygląda jak galareta. Co zrobić?

**Gemini:** Włącz **Auto Smooth** w zakładce Normals (kąt ok. 30 stopni). To sprawi, że płaskie powierzchnie pozostaną płaskie, a łuki zostaną wygładzone.

**Ivan:** Po Mirrorze turbina stała się przezroczysta.

**Gemini:** To błąd normalnych (odwrócone ścianki). W Edit Mode zaznacz wszystko (A) i naciśnij Alt + N -> Recalculate Outside.

---

### Sekcja Mikity Tsarkovicha (Konsultacje z Gemini):
**Mikita:** Odpowiadam za kadłub i przednią szybę. Od czego najlepiej zacząć modelowanie?

**Gemini:** Zacznij od cylindra (24–32 wierzchołki). Użyj Proportional Editing (O), aby aerodynamicznie zwęzić przód i tył. Zobacz tutorial: [Blender Beginner Hard Surface Modeling].

**Mikita:** Przód samolotu wygląda nienaturalnie po dodaniu Subdivision Surface.

**Gemini:** Dodaj wspierające krawędzie (support loops) blisko dziobu. Zobacz techniki tutaj: [Subdivision Surface Modeling Tips - Josh Gambrell].

**Mikita:** Szyba ma być matowa i nieprzezroczysta. Jak ustawić materiał?

**Gemini:** W Principled BSDF ustaw Transmission na 0, a Roughness na 0.6–0.8. Więcej o materiałach: [Blender Materials Beginner Guide - Blender Guru].

**Mikita:** Czy szybę należy oddzielić?

**Gemini:** Tak. Zaznacz faces i użyj P → Selection. Pozwoli to na niezależny shading i nakładanie osobnych materiałów bez wpływania na kadłub.

---

### Sekcja Daniila Yakauleva (Konsultacje z ChatGPT):
**Daniil:** Robię skrzydła z referencji. Najpierw grube czy płaskie?

**ChatGPT:** Zacznij od płaskiego Plane, dopasuj kształt do widoku z góry, a potem dodaj grubość przez Extrude (E). To najbezpieczniejsza metoda low-poly.

**Daniil:** Boję się, że skrzydła nie będą symetryczne przy ręcznym ustawianiu.

**ChatGPT:** Użyj modyfikatora Mirror z kadłubem jako punktem odniesienia. Pamiętaj o zresetowaniu transformacji (Ctrl + A), jeśli skrzydła „uciekają”.

**Daniil:** Skrzydła wyglądają jak z gumy po Shade Smooth.

**ChatGPT:** Włącz Auto Smooth i sprawdź podwójne wierzchołki: [Blender - How to fix Shading Issues (Merge by Distance)].

**Daniil:** Chcę dodać małe detale techniczne na spodzie. Nie obciążę modelu?

**ChatGPT:** W low-poly kilka prostych brył (anteny, osłony) nie wpłynie na wydajność. Liczy się oszczędna geometria.

**Daniil:** Po imporcie do wspólnego pliku wszystko działa, części poruszają się razem z kadłubem.

**ChatGPT:** Świetnie, użyliście poprawnej relacji Parent-Child (Ctrl+P). To najlepszy sposób na integrację pracy zespołowej.
