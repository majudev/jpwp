# Funkcyjny paradygmat programowania w języku Java

## Zanim zaczniemy
Przed rozpoczęciem zadań musisz zaintalować sobie środowisko IntelliJ IDEA. Waży ono 1GB, więc zacznij pobieranie już teraz!
- Dla Linuxa: 
  1. Pobierz paczkę stąd: [https://download.jetbrains.com/idea/ideaIC-2023.1.tar.gz](https://download.jetbrains.com/idea/ideaIC-2023.1.tar.gz)
  2. Wypakuj paczkę w dowolne miejsce
  3. `cd nazwa-folderu && cd bin && ./idea.sh`
- Dla Windowsa: 
  1. Pobierz paczkę stąd: [https://download.jetbrains.com/idea/ideaIC-2023.1.exe](https://download.jetbrains.com/idea/ideaIC-2023.1.exe)
  2. Zainstaluj
  3. Uruchom jak każdy inny program
- Dla Maca:
  1. Pobierz paczkę stąd: [https://download.jetbrains.com/idea/ideaIC-2023.1.dmg](https://download.jetbrains.com/idea/ideaIC-2023.1.dmg). Jeśli masz Apple M1, to użyj tego linku: [https://download.jetbrains.com/idea/ideaIC-2023.1-aarch64.dmg](https://download.jetbrains.com/idea/ideaIC-2023.1-aarch64.dmg)
  2. Zainstaluj
  3. Uruchom jak każdy inny program
  
__Nie musisz__ klonować tego repozytorium. Postępuj według instrukcji z README.

## Instrukcja 
#### Prezentacja
Naszą prezentację można zobaczyć tutaj: [https://docs.google.com/presentation/d/1skezON8RBjkOExSq_KoxbPYj0Exskzl6HjOwDria5LM/edit?usp=sharing](https://docs.google.com/presentation/d/1skezON8RBjkOExSq_KoxbPYj0Exskzl6HjOwDria5LM/edit?usp=sharing)

### Przykład 1. - aplikacja licząca średnią ważoną
Pobierz [wersję obiektową](%C5%9Arednia%20wa%C5%BCona%20obiektowo.zip) i [wersję funkcyjną](%C5%9Arednia%20wa%C5%BCona%20funcyjnie.zip).
Rozpakuj obydwa archiwa. Porównaj kod.

Zwróć uwagę, w jaki sposób są reprezentowane dane wejściowe (liczby i ich wagi).

Zwróć uwagę, że nigdy nie modyfikujemy danych wejściowych, a zawsze ich kopię.

### Przykład 2. - aplikacja okienkowa
Pobierz [wersję obiektową](ListaZada%C5%84%20obiektowo.zip) i [wersję funkcyjną](ListaZada%C5%84%20funkcyjnie.zip).
Rozpakuj obydwa archiwa. Porównaj kod.

Zwróć uwagę, że nie cały kod jest funkcyjny. Spróbuj podać powód dlaczego.

Zwróć uwagę, jak jest dodawany nowy element do listy w wersji funkcyjnej. Jeśli nie rozumiesz tego kawałka kodu, zapytaj autora kodu o co chodzi.

### Zadanie 1. - algorytm liczenia silni
1. Pobierz [wersję obiektową](Silnia%20obiektowo.zip). Rozpakuj archiwum. Zapoznaj się z kodem.
2. Spróbuj zmienić kod w taki sposób, żeby wykorzystywał funkcyjny paradygmat programowania.
  - Podpowiedź: pamiętaj, że przede wszystkim będziesz musiał zdefiniować jakieś funkcje. Zastanów się, co powinny robić.
  - Podpowiedź: pamiętaj, że nie możesz modyfikować obiektów. Każda funkcja powinna zwracać nowy obiekt. W Javie łatwo zrobić błąd.
    ```java
    function String dummy(final String s1){
      String s2 = s1;
      return s2;
    }
    ```
    Powyższy kod __nie zwraca__ nowego obiektu!! Zwraca on __ten sam__ obiekt, ponieważ Java operuje na referencjach! Poprawny kod to:
    ```java
    function String dummy(final String s1){
      String s2 = s1.clone();
      return s2;
    }
    ```
    Wyjątek to liczby. One domyślnie są immutable w Javie i możemy przypisywać je jak w 1 przykładzie (int, double, itp.)

### Zadanie 2. - algorytm Monte Carlo
1. Pobierz [wersję obiektową](Monte%20Carlo%20obiektowo.zip). Rozpakuj archiwum. Zapoznaj się z kodem.
2. Spróbuj zmienić kod w taki sposób, żeby wykorzystywał funkcyjny paradygmat programowania. Użyj rekurencji.
  - Podpowiedź: przypomnij sobie, jak były zapisywane listy w przykładzie z aplikacją okienkową.
  - Podpowiedź: __koniecznie__ zacznij od zmiany `int iterations` na `1000`. Na razie nie pytaj dlaczego.
3. Uruchom swój program kilka razy. Jeżeli zazwyczaj liczba pi przybliża się jako 3.08-3.20 to jest ok.
4. Spróbuj zwiększyć `iterations` na taką samą wartość jak w wersji obiektowej. Czy program działa? Jeśli nie, to dlaczego?

### Zadanie 3. - algorytm Monte Carlo który działa
1. Napraw poprzedni program, aby działał dla takiej samej wartości iterations, jak wersja obiektowa.
  - Podpowiedź: nie używaj rekurencji.
