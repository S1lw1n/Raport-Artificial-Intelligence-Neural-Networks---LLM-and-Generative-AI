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

**Ja:** Cześć! Razem z dwoma kolegami z grupy robimy na zaliczenie model 3D samolotu pasażerskiego w Blenderze. Mamy już bazowy kadłub, ale teraz moja kolej na detale. Muszę dodać okna i drzwi. Próbowałem użyć Booleana, żeby wyciąć dziury, ale na okrągłym fuzelażu wszystko się gnie i cieniowanie wygląda fatalnie. Jak to ugryźć?

**Gemini:** Cześć! Boolean przy zaokrąglonych powierzchniach to najkrótsza droga do błędów w cieniowaniu. Na okrągłym kadłubie najlepiej użyć funkcji **Knife Project**. Pozwala ona rzutować płaski kształt na zakrzywioną powierzchnię. Narysuj obrys okna jako osobny obiekt (Plane), ustaw go przed samolotem i rzutuj na model. To zachowa gładkość bazy.

**Ja:** Próbowałem tego Knife Project, ale szczerze mówiąc, u mnie to w ogóle nie reaguje. Klikam w menu i nic się nie wycina, albo dostaję błąd, że nie znaleziono obiektów do cięcia. Masz jakiś konkretny filmik, który pokazuje to krok po kroku?

**Gemini:** Kolejność zaznaczania i tryb są tu kluczowe. Zobacz ten krótki tutorial: [Blender Knife Project tool quick guide]. Pamiętaj: najpierw zaznaczasz w Object Mode swój „nóż” (obrys okna), potem z Shiftem kadłub, wchodzisz w Edit Mode i dopiero wybierasz z menu na górze Mesh > Knife Project.

**Ja:** Obejrzałem, robię dokładnie tak samo i dalej nic. Wycina mi dziury w jakichś dziwnych miejscach albo dostaję komunikat "No mesh objects found to cut". Co jeszcze może być nie tak? Przecież ustawiam okno prosto przed samolotem.

**Gemini:** Knife Project działa w oparciu o to, co aktualnie widzi Twoja kamera w rzutni. Jeśli patrzysz pod kątem, cięcie będzie krzywe lub nie trafi w obiekt. Musisz przejść do widoku ortograficznego (klawisz Numpad 3 dla widoku z boku). Zobacz ten drugi, bardziej szczegółowy filmik, który wyjaśnia błędy z pozycjonowaniem kamery: [Why Knife Project is NOT working - Blender Tutorial]. Upewnij się, że Twój „nóż” jest idealnie przed kadłubem i patrzysz na nich prosto z boku.

**Ja:** Dobra, teraz w końcu załapało! Widok ortograficzny to był brakujący element. Ale teraz pojawił się kolejny problem – jak wyciąłem te otwory, to widać, że samolot jest pusty w środku. Wygląda to słabo. Muszę teraz modelować fotele i całe wnętrze? Nie dam rady tego zrobić, to za dużo roboty.

**Gemini:** Absolutnie nie modeluj środka. Skoro projekt ma być prosty, zrób **okna „na czarno”**. Zamiast wycinać dziury na wylot, po prostu zostaw te wycięte kształty jako część siatki kadłuba, ale przypisz im osobny, czarny materiał z niskim parametrem Roughness (ok. 0.1). To stworzy efekt przyciemnianych szyb i całkowicie ukryje pusty środek.

**Ja:** Dzięki, dobry pomysł. Zrobiłem czarny materiał i od razu model wygląda poważniej. Teraz biorę się za turbiny. Szczerze nie mam pojęcia, jak zacząć modelować taki silnik, żeby nie był tylko zwykłym klocem. Masz jakieś wideo o modelowaniu turbin z cylindrów?

**Gemini:** Turbinę najlepiej budować modułowo z cylindrów. Zobacz te tutoriale, pomogą Ci zrozumieć workflow: [Modeling a simple Jet Engine in Blender]. Zacznij od jednego cylindra na obudowę, użyj funkcji Inset (I) oraz Extrude (E) do środka, żeby stworzyć wlot. Dzięki temu turbina będzie miała głębię.

**Ja:** Wymodelowałem turbinę, ale mam problem z jej wygładzaniem. Jak włączam „Shade Smooth”, to cały silnik wygląda jak zgnieciona galareta, krawędzie, które powinny być ostre, są rozmyte. Co z tym zrobić?

**Gemini:** To problem z normalnymi. Musisz włączyć funkcję **Auto Smooth**. Wejdź w zakładkę Data Properties (zielony trójkąt), rozwiń sekcję Normals i zaznacz Auto Smooth (ustaw kąt na ok. 30 stopni). To sprawi, że płaskie powierzchnie turbiny zostaną płaskie, a tylko boki będą zaokrąglone.

**Ja:** Super, teraz silnik wygląda dobrze. Teraz muszę go skopiować pod drugie skrzydło. Próbowałem to zrobić ręcznie, ale nigdy nie trafiam w to samo miejsce. Jak to zrobić idealnie symetrycznie?

**Gemini:** Użyj modyfikatora **Mirror**. Wybierz turbinę. Dodaj modyfikator Mirror. W polu „Mirror Object” kliknij pipetę i zaznacz kadłub samolotu jako punkt odniesienia. Jeśli turbina wyskoczy w dziwnym miejscu, zaznacz ją i naciśnij **Ctrl + A -> All Transforms**. To zresetuje jej pozycję bazową i Mirror zadziała idealnie.

**Ja:** Spróbowałem, ale ta nowa turbina po drugiej stronie stała się przezroczysta, jakbym patrzył przez nią na wylot. Co się stało?

**Gemini:** To problem z Normalnymi (Normals), które Mirror czasem odwraca „na lewą stronę”. Zaznacz turbinę, wejdź w Edit Mode, zaznacz całą siatkę (klawisz A) i naciśnij **Alt + N -> Recalculate Outside**. To naprawi kierunek ścianek i turbina będzie widoczna poprawnie.

**Ja:** Pomogło, dzięki. Ostatnie co zostało mi zrobić to podwozie. Zrobiłem koła, ale mamy problem z integracją plików. Jak koledzy ruszają samolotem w swoim pliku głównym, to moje podwozie zostaje w punkcie zero. Muszę to wszystko łączyć w jedną siatkę (Join)?

**Gemini:** Nie używaj funkcji Join, bo stracisz kontrolę nad materiałami. Użyj **Parentingu**. Zaznacz wszystkie elementy podwozia i turbiny, na samym końcu zaznacz kadłub i naciśnij **Ctrl + P -> Object**. W ten sposób kadłub zostanie „rodzicem” – jak koledzy przesuną samolot, Twoje detale polecą razem z nim.

**Ja:** Dzięki! Wszystko działa i wygląda dokładnie tak, jak chcieliśmy.

---

### Sekcja Mikity Tsarkovicha (Konsultacje z Gemini):
**Ja:** Robię model samolotu w Blenderze. Odpowiadam za kadłub i przednią szybę. Od czego najlepiej zacząć modelowanie kadłuba?

**Gemini:** Najlepiej zacząć od prostego cylindra jako bazy. Ustaw około 24–32 verteksy, aby zachować odpowiednią ilość detalu. Następnie dopasuj proporcje na podstawie referencji — widok z boku i z góry będzie najważniejszy.

**Ja:** Jak poprawnie ustawić proporcje kadłuba?

**Gemini:** Wejdź w Edit Mode i użyj Scale (S) oraz Proportional Editing (O). Zwęż przód i tył, aby uzyskać aerodynamiczny kształt. Dodaj edge loopy (Ctrl+R), żeby lepiej kontrolować krzywizny. Możesz też obejrzeć poradniki na YouTube: „Blender Beginner Hard Surface Modeling” – Blender Guru oraz „Modeling a Jet Airplane in Blender” – CG Cookie.

**Ja:** Jak wymodelować przód samolotu, żeby wyglądał realistycznie?

**Gemini:** Dodaj więcej geometrii w przedniej części modelu. Użyj Subdivision Surface modifier, a następnie dodaj supporting edge loopy blisko krawędzi, aby zachować kontrolę nad kształtem. Pomocny może być poradnik: „Subdivision Surface Modeling Tips” – Josh Gambrell.

**Ja:** Modeluję teraz przednią szybę. Ma być matowa i nieprzezroczysta. Jak ustawić materiał?

**Gemini:** Dodaj nowy materiał z shaderem Principled BSDF. Ustaw Transmission na 0, aby szyba była nieprzezroczysta. Zwiększ Roughness do około 0.6–0.8, aby uzyskać efekt matowy. Możesz ustawić ciemnoszary kolor. Jeśli potrzebujesz dodatkowych informacji: „Blender Materials Beginner Guide” – Blender Guru.

**Ja:** Czy szybę należy oddzielić jako osobny obiekt?

**Gemini:** Tak. W Edit Mode zaznacz faces szyby i użyj **P → Selection**. Dzięki temu możesz niezależnie zarządzać materiałem oraz ustawieniami shadingu.

**Ja:** Pojawiają się problemy z cieniowaniem. Jak je poprawić?

**Gemini:** Użyj Shade Smooth, następnie włącz **Auto Smooth** w Object Data Properties (np. 30°). Sprawdź również, czy nie ma podwójnych verteksów — użyj **Merge by Distance**. Możesz obejrzeć: „Fix Shading Problems in Blender” – CG Cookie.

**Ja:** Jak poprawić realizm modelu?

**Gemini:** Dodaj delikatny Bevel na ostrych krawędziach. W rzeczywistości krawędzie nie są idealnie ostre. Użyj HDRI w ustawieniach World, aby uzyskać bardziej realistyczne oświetlenie. Polecany poradnik: „Lighting in Blender for Beginners” – Blender Guru.

**Ja:** Na tej podstawie dokończę model kadłuba i przednią szybę.

**Gemini:** Powodzenia przy dalszej pracy nad projektem!

---

### Sekcja Daniila Yakauleva (Konsultacje z ChatGPT):
**Ja:** Cześć! Przygotowałem już referencje dla zespołu. Na ich bazie chcę zacząć od skrzydeł, ale nie wiem, czy od razu robić je grube, czy najpierw płaskie?

**ChatGPT:** Cześć! Najlepiej zacząć od płaskiej geometrii (Plane) widzianej z góry. Dopasuj obrys do rzutu, a dopiero później dodaj grubość przez *Extrude*. Dzięki temu łatwiej będzie Ci kontrolować proporcje końcówek skrzydeł bez walki z grubością od samego początku.

**Ja:** Okej, zrobiłem jedno skrzydło, ale cały czas mam wrażenie, że kąt nachylenia jest trochę dziwny. Jak patrzę z góry jest ok, ale z boku wygląda to nienaturalnie.

**ChatGPT:** To klasyczny problem przy przechodzeniu z 2D do 3D. Sprawdź skrzydło jednocześnie w widoku z góry i z boku (użyj widoków ortograficznych). Drobna korekta rotacji względem osi Y często wystarcza, by nadać mu tzw. wznios (dihedral angle). Zobacz ten poradnik o nawigacji: [YouTube: Blender 3D Viewport Navigation and Orthographic Views].

**Ja:** Próbuję zrobić drugie skrzydło modyfikatorem Mirror, ale ono pojawia się w środku tego pierwszego albo gdzieś daleko od samolotu. Co robię źle?

**ChatGPT:** Modyfikator Mirror działa względem punktu *Origin* obiektu. Jeśli przesuwałeś skrzydło w Object Mode, jego punkt środkowy jest w złym miejscu. Zaznacz skrzydło i naciśnij **Ctrl + A -> All Transforms**. Możesz też w modyfikatorze Mirror wybrać "Mirror Object" i wskazać pipetą kadłub Mikity – wtedy skrzydło odbije się idealnie względem osi samolotu. Zobacz, jak to działa tutaj: [YouTube: Blender Mirror Modifier Tutorial].

**Ja:** Skrzydła są już na miejscu, ale po włączeniu *Shade Smooth* wyglądają zbyt miękko, jakby były z gumy. Krawędź natarcia powinna być wyraźniejsza.

**ChatGPT:** Spróbuj włączyć funkcję **Auto Smooth** (zakładka Object Data Properties > Normals) i ustaw kąt na około 30-40 stopni. To pozwoli zachować ostre krawędzie tam, gdzie są potrzebne, a wygładzić płaskie powierzchnie. Jeśli cieniowanie nadal „pływa”, sprawdź, czy nie masz podwójnych wierzchołków po operacjach Extrude. Użyj: [YouTube: Blender - How to fix Shading Issues (Merge by Distance)].

**Ja:** Teraz cały model wygląda trochę zbyt prosty. Chciałbym dodać coś jeszcze od siebie, żeby dół samolotu nie był taki pusty, ale nie chcę przesadzić z detalami.

**ChatGPT:** Możesz dodać kilka drobnych elementów technicznych na spodzie kadłuba, np. anteny, obudowy systemów łączności lub małe wypustki aerodynamiczne. W stylu low-poly nie musisz odwzorowywać ich idealnie – wystarczą proste bryły (cylindry, sześciany). To nada modelowi „skali” i realizmu.

**Ja:** Dodałem parę takich elementów, ale boję się, że model stanie się za ciężki i będzie zacinać Blender kolegów przy integracji.

**ChatGPT:** Jeśli to są proste bryły (kilkanaście wierzchołków na element), nie wpłynie to znacząco na wydajność. W low-poly liczy się umiar. Unikaj tylko dodawania modyfikatora *Subdivision Surface* na każdym małym obiekcie, a wszystko będzie działać płynnie.

**Ja:** Wizualnie wygląda to teraz świetnie. Teraz muszę to wszystko połączyć z plikiem, który mają koledzy. Czy muszę te wszystkie anteny i skrzydła łączyć w jeden obiekt funkcją Join?

**ChatGPT:** Odradzam Join, bo trudniej będzie potem zmieniać materiały. Najlepszym rozwiązaniem jest **Parenting**. Zaznacz wszystkie swoje detale, na samym końcu zaznacz kadłub (jako obiekt nadrzędny) i naciśnij **Ctrl + P -> Object**. Dzięki temu kadłub będzie „rodzicem” – gdy koledzy go przesuną, Twoje skrzydła i anteny polecą razem z nim. Zobacz, jak zarządzać hierarchią: [YouTube: Parenting objects in Blender].

**Ja:** Po imporcie do wspólnego pliku wszystko działa! Skrzydła i detale poruszają się razem z kadłubem, a skala pasuje do tego, co zrobili Ivan i Mikita.

**ChatGPT:** Super! Poprawny Parenting to podstawa pracy zespołowej w 3D. Wasz wspólny model jest teraz gotowy do dalszej obróbki.

**ChatGPT:** Super. W takim razie Twoja część modelu jest gotowa i można przejść do dalszej pracy zespołowej.
