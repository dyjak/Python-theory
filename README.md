# Python-theory
Script language lectures


# Język skryptowy lab1

### Pierwszy program

Rozpocznijmy od stworzenia krótkiego programu który wyświetla „Hello world!”. W Pythonie, użyjemy polecenia print do
wyświetlenia tekstu. Poniżej przedstawiono gotowy skrypt.
```Python
print('Hello world!')
```
Dla porównania poniżej przedstawiono program napisany w języku Java:
```Java
public class HelloWorld {

  public static void main(String[] args) {
    System.out.println("Hello, World");
  }
}
```
Jak widać program napisany w Javie wykonuje dokładnie tą samą czynność a jest dużo bardziej „skomplikowany”. Zatem
programowanie w Pythonie jest prostsze.
Proste operacje
Python ma zdolność do wykonywania obliczeń. Wprowadź obliczenia bezpośrednio do konsoli Pythona a ona zwróci odpowiedź.
```Python
>>> 2 + 2
4
>>> 5 - 2 + 4
7
>>> (-7 + 2) * (-4)
20
>>> 6/0
Traceback (most recent call last):
File "<pyshell#0>", line 1, in <module>
6/0
ZeroDivisionError: integer division or modulo by zero
```
> W Pythonie ostatnia linia komunikatu o błędzie informuje o rodzaju błędu:exclamation:

### Operatory
| Operator numeryczny | opis             |
|---------------------|------------------|
| x + y               | suma x oraz y    |
| x - y               | różnica x oraz y |
| x * y               | iloczyn x oraz y |
| x / y               | iloraz x oraz y  |
| x // y              | (zaokrąglony w dół) iloraz x oraz y  |
| x % y               | reszta z dzielenia x / y  |
| abs(x)              | wartość bezwzględna x  |
| divmod(x, y)        | para (x // y, x % y)  |
| pow(x, y)           | x do potęgi y  |
| x ** y              | x do potęgi y  |
| x += y              | x = x + 1        |
| x -= y              | x = x - 1        |
| x *= y              | x = x * 1        |
| x /= y              | x = x / 1        |

| Operator porównania | opis             |
|---------------------|------------------|
| x != y               | rózne    |
| x == y               | równe |
| x > y                | większe |
| x < y                | mniejsze  |
| x >= y               | większe lub równe  |
| x <= y               | mniejsze lub równe  |

Wiele innych języków ma specjalne operatory, takie jak "++" jako skrót dla "x += 1". Python ich nie ma.
### Operacje na łańcuchach znaków (stringach)
Przy „tworzeniu” skryptu wypisującego na ekran komunikat Hello world! tekst umieszczany był w pojedynczych apostrofach (’text’)
ten sam efekt otrzymamy również gdy napis zostanie zamknięty w cudzysłów (”text”). Gdy napis wymagał będzie użycia apostrofu
(np. He’s) wystarczy przed apostrofem postawić znak `\`. Wypróbuj przedstawione konstrukcje.
> Backslash może być również użyty przy tabulatorach, przejściu do następnej linii, dowolnych znakach Unicode i różnych innych rzeczy, których nie można w rzeczywisty sposób wydrukować.

Do konkatenacji służy operator `+` podczas łączenia łańcuchów znaków nie ma znaczenia czy zostały one utworzone w pojedynczym czy podwójnym cudzysłowie. Łańcuchy znaków można również pomnożyć przez liczbę całkowitą np. `”spam”*4` sprawdź jaki będzie wynik takiego działania. Przydatny może być również operator indeksowania który przedstawiono w poniższym skrypcie. Wykonaj go w środowisku Pythona i sprawdź rezultat.
```Python
a = "Welcome to Python's world!"
print(a[0])
print(a[0:7])
```
### Wprowadzanie danych
Przydatną funkcją jest możliwość wprowadzania danych przez użytkownika do tego służy instrukcja `input` i ma ona postać:
```Python
input("stosowny komunikat").
```
### Konwertowanie typów
Jest to zamiana zmiennej z jednego typu na zmienną innego typu np. `float(2)` zamieni liczbę całkowita na zmiennoprzecinkową.
### Zmienne
Zmienne odgrywają bardzo ważną rolę w większości języków programowania, a Python nie jest wyjątkiem. zmienna umożliwia
zapisanie wartości przez przypisanie jej do nazwy, którą można wykorzystać do odnoszenia się do wartości później w programie. Aby
przypisać zmienną, użyj jednego znaku równości.
```Python
>>> x = 7
>>> print(x)
7
>>> print(x + 3)
10
>>> print(x)
7
```
Zmienna może być ponownie przypisana tyle razy, ile chcesz, aby
zmienić ich wartość.
```Python
>>> x = 123
>>> print(x)
123
>>> x = "To jest napis"
>>> print(x + "!")
To jest napis!
```
>W Pythonie zmienne nie mają określonych typów, więc można przypisać łańcuch znaków do zmiennej, a później przypisać liczbę całkowitą do tej samej zmiennej

Obowiązują pewne ograniczenia dotyczące znaków, które mogą być używane w nazwach zmiennych Pythona. Dozwolone są tylko
litery, cyfry i podkreślenia. Ponadto nie mogą zaczynać się od liczb. Nieprzestrzeganie tych zasad powoduje błędy.
```Python
to_poprawna_nazwa_zmiennej = 7
123abc = 7
SyntaxError: invalid syntax
```
>Python to język programowania z uwzględnieniem wielkości liter. Tak więc, Lastname i lastname to dwie różne nazwy zmiennych w Pythonie.
Próba odniesienia do zmiennej, która nie została przypisana powoduje błąd. możesz użyć instrukcji `del`, aby usunąć zmienną, co oznacza, że odwołanie od nazwy do wartości zostanie usunięte, a próba użycia zmiennej spowoduje błąd. Usunięte zmienne mogą być ponownie przypisane do późniejszego stanu, tak jak zwykle.
```Python
>>> foo = "napis"
>>> foo
'napis'
>>> bar
NameError: name 'bar' is not defined
>>> del foo
>>> foo
NameError: name 'foo' is not defined
```
>Zmienne `foo` i `bar` są nazywane zmiennymi metasyntaktycznymi, co oznacza, że są one używane jako nazwy zastępcze w przykładowym kodzie, aby coś zademonstrować. `Spam` i `eggs` są kanonicznymi zmiennymi metasyntaktycznymi używanymi w Pythonie. Nawiązują one do słynnego skeczu Latającego Cyrku Monty Pythona.

### Instrukcja warunkowa IF
Możesz użyć instrukcji `if`, aby wykonać fragment kodu, jeśli spełniony jest określony warunek. Jeśli wyrażenie ma wartość `True`, wykonywane są pewne instrukcje. W przeciwnym razie są one pomijane. Instrukcja `if` wygląda następująco:
```Python
if wyrażenie warunkowe:
  instrukcje
```
Python używa wcięć (białe znaki na początku linii), aby ograniczyć bloki kodu. Inne języki, takie jak C czy Java, używają nawiasów klamrowych, aby to osiągnąć, ale w języku Python obowiązkowe jest wcięcie; programy nie będą działać bez niego. Jak widać, każda z instrukcji w bloku instrukcji `if` powinna być poprzedzona wcięciem.
Przykład:
```Python
if 10 > 5:
  print("10 jest większe od 5")
print("koniec skryptu")
```
Aby wykonać bardziej złożone warunki, instrukcje mogą być zagnieżdżone, jedna w drugiej. Oznacza to, że wewnętrzne instrukcje `if` są częścią instrukcji zewnętrznej. Jest to jeden ze sposobów sprawdzenia, czy spełnione są warunki wielokrotne.
Przykład:
```Python
if num > 5:
  print("Więcej niz 5")
  if num <= 45:
    print("Wartość z przedziału (5; 45]")
```
Instrukcja `else` wykonuje instrukcję `if` i zawiera kod, który jest wywoływany, gdy instrukcja `if` zwraca wartość `False`. Podobnie jak w przypadku instrukcji `if`, kod wewnątrz bloku powinien być wcięty.
Przykład:
```Python
x = 4
if x == 5:
  print("Tak")
else:
  print("Nie")
```
Instrukcje `if` i `else` można łączyć łańcuchowo, aby określić, która opcja w serii możliwości jest prawdziwa.
Przykład:
```Python
num = 12
if num == 5:
  print("Numerem jest 5")
else:
  if num == 10:
    print("Numerem jest 10")
  else:
    print("Numerem nie jest 5 ani 10")
```
Instrukcja `elif` jest skrótem do użycia podczas łączenia instrukcji `if` i `else`. Seria instrukcji `if` `elif` może mieć końcowy blok `else`, który jest wywoływany, jeśli żadne z wyrażeń `if` lub `elif` nie jest prawdziwe.
Przykład:
```Python
num = 12
if num == 5:
  print("Numerem jest 5")
elif num == 10:
  print("Numerem jest 10")
elif num == 15:
  print("Numerem jest 10")
else:
  print("Numerem nie jest 5, 10 ani 15")
```
### Operatory logiczne
Służą do tworzenia bardziej skomplikowanych warunków dla instrukcji, które opierają się na więcej niż jednym warunku. Operatorami logicznymi w Pythonie są `and`, `or`, i `not`.
Operator `and` bierze dwa argumenty i ocenia je jako prawda wtedy i tylko wtedy, gdy oba argumenty są prawdziwe. W przeciwnym razie wartość ta jest fałszywa. Operator `or` także bierze dwa argumenty i ocenia je jako prawda wtedy, gdy co najmniej jeden z nich jest prawdziwy. W przeciwnym razie wartość ta jest fałszywa. Operator `not` bierze tylko jeden argument i neguje go. 
>Python używa słów dla swoich operatorów logicznych, podczas gdy większość innych języków używa symboli takich jak &&, || i !.

### Priorytet operatorów
Jest bardzo ważną koncepcją programowania. Jest to rozszerzenie matematycznej koncepcji porządku operacji (kolejność wykonywania działań mnożenie dokonywane przed dodaniem itp.) W celu włączenia innych operatorów, takich jak operatorów logicznych.
Poniższy kod pokazuje, że `==` ma wyższy priorytet niż `or`:
```Python
>>> False == False or True
True
>>> False == (False or True)
False
>>> (False == False) or True
```
>Kolejność operacji Pythona jest taka sama jak w przypadku normalnej matematyki: najpierw nawiasy, potem potęgowanie, potem mnożenie / dzielenie, a następnie dodawanie / odejmowanie.
Poniższa tabela zawiera listę wszystkich operatorów Pythona, od najwyższego priorytetu do najniższego.

| Lp. | Operator | Opis                                                                 | Lp. | Operator               | Opis                                                        |
|-----|----------|----------------------------------------------------------------------|-----|------------------------|-------------------------------------------------------------|
| 1   |    **    |                              potęgowanie                             | 8   | <= < > >=              | mniejsze bądź równe, mniejsze, większe, większe bądź równe  |
| 2   |   ~ + -  |               dopełnienie binarne, unarny plus i minus               | 9   | == !=                  | równe, różne                                                |
| 3   | * / % // | mnożenie, dzielenie, reszta z dzielenia, cześć całkowita z dzielenia | 10  | += %= /= //= -= *= **= | skrótowe operatory                                          |
| 4   |    + -   |                        dodawanie i odejmowanie                       | 11  | is, is not             | operatory tożsamości                                        |
| 5   | << >>    | przesunięcie bitowe w lewo i w prawo                                 | 12  | in, not in             | operatory zawierania                                        |
| 6   | &        | AND na bitach                                                        | 13  | not, or, and           | operatory logiczne                                          |
| 7   | ^ \|     | XOR i OR na bitach                                                   |     |                        |                                                             |

### Pętla while
Instrukcja `if` jest uruchamiana jednokrotnie, jeśli jej warunek jest prawdziwy, a nigdy, jeśli oceniany jest jako fałszywy. Instrukcja `while` jest podobna, z tym wyjątkiem, że może być uruchamiana więcej niż raz. Instrukcje wewnątrz niej są wielokrotnie wykonywane, o ile warunek jest prawdziwy. Po przejściu do wartości False wykonywana jest następna sekcja kodu. Poniżej znajduje się pętla `while` zawierająca zmienną, która liczy od 1 do 5, w którym to momencie pętla kończy się.
```Python
i = 1
while i <= 5:
  print(i)
  i = i + 1
print("Koniec!")
```
Nieskończona pętla jest specjalnym rodzajem pętli while; nigdy się nie kończy. Jego stan pozostaje zawsze prawdziwy.
Przykład:
```Python
while 1 == 1:
  print("operacje w pętli")
```
Aby przedwcześnie zakończyć pętlę, można użyć instrukcji break. Po napotkaniu wewnątrz pętli instrukcja break powoduje natychmiastowe zakończenie pętli.
Przykład:
```Python
i = 0
while 1 == 1:
  print(i)
  i = i + 1
  if i >= 5:
    print("Przerwanie")
    break
print("Koniec")
```
Kolejną instrukcją, która może być używana w pętlach, jest
continue. W przeciwieństwie do break, continue przeskakuje
z powrotem na początek pętli, zamiast ją zatrzymywać.
Przykład:
```Python
i = 0
while True:
  i = i +1
  if i == 2:
    print("Pomiń 2")
    continue
  if i == 5:
    print("Przerwanie")
    break
  print(i)
print("Koniec")
```

### Listy
Listy są innym typem obiektu w Pythonie. Służą do przechowywania indeksowanej listy pozycji. Listę tworzy się za pomocą nawiasów kwadratowych z przecinkami oddzielającymi elementy. Dostęp do określonej pozycji na liście można uzyskać za pomocą jej indeksu w nawiasach kwadratowych.
>Listy indeksujemy od 0.
Przykład:
```Python
words = ["Hello", "world", "!"]
print(words[0])
print(words[1])
print(words[2])
```
Pusta lista tworzona jest przez pustą parę nawiasów kwadratowych.
Zazwyczaj lista będzie zawierała elementy jednego typu, ale możliwe jest również uwzględnienie kilku różnych typów. Listy można
również zagnieżdżać w innych listach.
Przykład:
```Python
number = 3
things = ["string", 0, [1, 2, number], 4.56]
print(things[1])
print(things[2])
print(things[2][2])
```
>Listy są często używane do reprezentowania siatek 2D, ponieważ w Pythonie brakuje wielowymiarowych tablic, które byłyby używane w innych językach.

Indeksowanie wykraczające poza granice list powoduje błąd `IndexError`. Niektóre typy, takie jak łańcuchy znaków, mogą być indeksowane jak listy. Indeksowane łańcuchy zachowują się tak, jak indeksowana lista przechowująca każdy znak osobno. W przypadku innych typów, takich jak liczby całkowite, indeksowanie ich nie jest możliwe i powoduje błąd `TypeError`.

###Operacje na listach
Elementowi listy o określonym indeksie można ponownie nadać nową wartość .

Przykład:
```Python
nums = [7, 7, 7, 7]
nums[2] = 5
print(nums)
```
Listy mogą być łączone i mnożone ze sobą tak samo łączone jak stringi.
Przykład:
```Python
nums = [1, 2, 3]
print(nums + [4, 5, 6])
print(nums * 3)
```

Aby sprawdzić, czy dany element znajduje się na liście, można użyć operatora `in`. Zwraca `True`, jeśli element występuje raz lub więcej razy na liście, a `False`, jeśli nie występuje.
Przykład:
```Python
words = ["spam", "egg"]
print("spam" in words)
print("sausages" in words)
```
Aby sprawdzić, czy dany element nie znajduje się na liście, możesz użyć operatora `not` w jeden z następujących sposobów:
Przykład:
```Python
nums = [1, 2, 3]
print(not 4 in nums)
print(4 not in nums)
print(not 3 in nums)
print(3 not in nums)
```
### Funkcje list
Innym sposobem modyfiakcji list jest użycie metody `append`. Spowoduje to dodanie elementu do końca istniejącej listy.
Przykład:
```Python
nums = [1, 2, 3]
nums.append(4)
print(nums)
```
Aby pobrać liczbę elementów w liście można użyć funkcji `len`.
Przykład:
```Python
nums = [4, 5, 6]
print(len(nums))
```
>W przeciwieństwie do `append`, `len` jest normalną funkcją, a nie metodą. Oznacza to, że jest ona napisana przed listą, dla której jest wywoływana, bez użycia kropki.

Metoda `insert` jest podobna do `append`, z tym wyjątkiem, że pozwala wstawić nowy element w dowolnej pozycji na liście, a nie tylko na końcu.
Przykład:
```Python
words = ['Python', 'cool']
words.insert(1, 'is')
print(words)
```
Metoda `index` znajduje pierwsze wystąpienie elementu listy i zwraca jego indeks. Jeśli element nie znajduje się na liście, wywołuje on błąd `ValueError`.
Przykład:
```Python
letters = ['q', 'w', 'e', 'r', 't', 'y']
print(letters.index('r'))
print(letters.index('a'))
```
Istnieje jeszcze kilka przydatnych funkcji i metod dla list.
`max(lista)`   Zwraca pozycję listy z maksymalną wartością
`min(lista)`   Zwraca pozycję listy z minimalną wartością
`lista.count(obj)`   Zwraca liczbę określającą, ile razy element występuje na liście
`lista.remove(obj)`  Usuwa obiekt z listy
`lista.reverse()`  Odwraca obiekty na liście
`lista.pop(i)`   Zwraca i-ty element listy i usuwa go
`lista.extend(seq)`  Dołącza zawartość seq do listy
`lista.sort(func)`   Sortuje obiekty z listy, użyj funkcji porównawczej func

### Pętla for
Pętla `for` iteruje po elementach np. listy w kolejności, wykonując blok instrukcji.
Przykład:
```Python
words = ["hello", "world", "spam", "eggs"]
for word in words:
  print(word + "!")
```
Pętla `for` jest zwykle używana do powtarzania fragmentu kodu pewną liczbę razy. Odbywa się to przez połączenie pętli z funkcją `range`.
Przykład:
```Python
for i in range(5):
  print(i)
```


[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/IEOj-sq2)
# Język skryptowy lab2

### Funkcje

Pewne funkcje użyte zostały już we wcześniejszej lekcji była nią np. funkcja `print()`. Były to gotowe funkcje dostarczone wraz z bibliotekami Pythona.
```Python
print("Hello world!")
a = []
a.extend(range(2, 20))
print(a)
print(str(12))
print(list(range(10, 20, 3)))
```

Poniżej przedstawiono przykład prostej funkcji jaką można napisać samemu. Każda nowo tworzona funkcja posiada nagłówek zbudowany ze słowa `def` nazwy funkcji oraz przyjmowanych przez nią argumentów umieszczonych w nawiasach. Potem jest oczywiście ciało funkcji wykonujące określone czynności. Funkcję wywołać można przez podanie jej nazwy oraz odpowiednich parametrów jakie przyjmuje. Prosta przykładowa funkcja oraz jej wywołanie zaprezentowano poniżej.
> Należy pamiętać, że blok kodu w każdej funkcji rozpoczyna się dwukropkiem i jest on wcięty:exclamation:
```Python
def my_func():
    print("spam")
    print("spam")
    print("spam")

my_func()
```
Żeby poprawnie wywołać funkcję należy ją napisać przed jej wywołaniem. Rezultatem poniższego wywołania kodu będzie błąd `NameError: name 'hello' is not definied`
```Python
hello()

def hello():
    print("hello")
```

### Komentarze
By ułatwić czytelność kodu stosuje się komentarze. W Pythonie komentarz jednolinowy zapisuje się przez znak `#` na początku komentowanej linii. Natomiast aby utworzyć komentarz wieloliniowy należy użyć potrójnych cudzysłowów.
```Python
def shout(word):
    """
    komentarz wieloliniowy
    """
    # komentarz jednoliniowy
    print(word + "!")

shout("spam")
```

### Argumenty funkcji
Argumenty funkcji używane są jak zmienne w ciele funkcji i nie mogą być użyte poza nią to samo dotyczy zmiennych utworzonych wewnątrz funkcji.
```Python
def print_with_exclamation(word):
    print(word + "!")
    
print_with_exclamation("spam")
print_with_exclamation("eggs")
print_with_exclamation("python")
```

```Python
def print_sum_twice(x, y):
    print(x + y)
    print(x + y)

print_sum_twice(2, 5)
```
Poniższa funkcja w swoim ciele używa parametru `var` który poza ciałem funkcji nie jest dostępny oznacza to, że te zmienne są lokalne
```Python
def function(var):
    var += 1
    print(var)

function(7)
print(var)
```
### Zwracanie wartości z funkcji
Pewne funkcje takie jak `int` lub `str` zwracają wartość, która może być użyta później. Aby funkcja mogła zwracać wartość musi zawierać słowo kluczowe `return`.
```Python
def max(x, y):
    if x >= y:
        return x
    else:
        return y

print(max(4, 6))
z = max(9, 3)
print(z)
```
Gdy na pewnym poziomie zagnieżdżenia kodu znajduje się słowo kluczowe `return` żadna z instrukcji, która zostanie napisana potem nie zostanie wykonana.
```Python
def add_numbers(x, y):
    sum = x + y
    return sum
    print("Ten napis nie wyświetli się")

print(add_numbers(4, 5))
```
### Funkcje jako obiekty
Chociaż są one tworzone inaczej niż normalne zmienne, funkcje są jak każda inna wartość. Można je przypisywać do zmiennych i nadpisywać, a następnie wywoływać ich z użyciem nazwy.
```Python
def multiply(x, y):
    return x * y

a = 4
b = 6
operation = multiply
print(operation(a, b))
```

### Funkcja jako argument innej funkcji
Poniżej przedstawiony został przykład jak do jednej z funkcji jako parametr podać inną funkcję
```Python
def add(x, y):
    return x + y

def do_twice(func, x, y):
    return func(func(x, y), func(x, y))

a = 5
b = 10
print(do_twice(add, a, b))
```

### Moduły
```Python
import random

for i in range(5):
    val = random.randint(1, 6)
    print(val)
```
> Aby zaimportować wszystkie obiekty z modułu należy wykorzystać * np `from math import *` :exclamation:
```Python
from math import pi

print(pi)
```
Jeśli wystąpi próba importu modułu, który nie jest dostępny np. `import dowolny_modul` generowany jest wyjątek `ImportError`

Importowane moduły lub wybrane obiekty w nich zawarte można używać pod inną nazwą przy pomocy definiowania dla nich słów kluczowych przy użyciu operatora `as`
```Python
from math import sqrt as square_root

print(square_root(100))
```

W Pythonie występuje 3 główne rodzaje modułów, napisane przez programistę, instalowane z dodatkowych źródeł oraz instalowane łącznie z Pythonem. Wywoływane wcześniej moduły znajdują się w standardowych bibliotekach Pythona. Python posiada wiele użytecznych modułów niektóre z nich umożliwiają opreacje na stringach, obiektach dat, operacje matematyczne, obsługi formatu json, działania na wielu watkach i wiele innych.
Wiele z dodatkowych modułów do Pythona znajduje się w PyPI (Python Package Index) aby w prosty sposób móc doinstalować jakiś moduł, który jest potrzebny należy wykorzystać program zwany `pip`. Aby zainstalować interesujący moduł wystarczy przejść do wiersza poleceń i wpisać komendę `pip install nazwa_biblioteki`, po jej zainstalowaniu można już swobodnie wykorzystać jej możliwości we własnym kodzie.

### Błędy
Błędy informują użytkownika o tym, że coś poszło nie tak. Gdy wykrywany jest błąd program natychmiast się zatrzymuje jednym z częstszych błędów jest błąd dotyczący dzielenia przez 0 i jest nim `ZeroDevisionError`
Innymi często występującymi błędami są:

:small_blue_diamond:`ImportError`

:small_blue_diamond:`IndexError`

:small_blue_diamond:`NameError`

:small_blue_diamond:`SyntaxError`

:small_blue_diamond:`TypeError`

:small_blue_diamond:`ValueError`

W celu obsługi wyjątku, który może wystąpić wykorzystuje się instrukcje `try/except`. Blok `try` może mieć wiele różnych bloków `except`, aby wyłapywać różne rodzaje błędów. Różne rodzaje błędów mogą być także umieszczone w jednym bloku `except`, aby wyłapywać wszystkie z nich i wykonać dla nich tę samą akcję.
```Python
try:
    var = 100
    print(var + "witaj")
    print(var / 2)
except ZeroDivisionError:
    print("Dzielenie przez 0")
except (ValueError, TypeError):
    print("jakiś błąd")
```
Możliwy jest też zapis bloku `exception` bez informacji o jakimkolwiek konkretnym błędzie można w ten sposób przechwycić wszystkie błędy jakie mogą wystąpić i wykonać dla nich tę samą akcję.
```Python
try:
    word = "spam"
    print(word / 0)
except:
    print("wykryto błąd")
```

#### Blok finally 
Umieszcza się za blokami `try` i `except`. Używany jest do wykonania jakiegoś fragmentu kodu bez względu na to czy wystąpi bądź nie wystąpi błąd w fragmencie kodu w bloku `try`
```Python
try:
    print("hello")
    # print(1/0)
except ZeroDivisionError:
    print("Dzielenie przez 0")
finally:
    print("Ta linia kodu wykona się zawsze o bloku try")
```

#### Instrukcja reise
Służy do poprawiania błędów trzeba podać typ zgłaszanego wyjątku
```Python
print(1)
raise ValueError
print(2)

name = "123"
raise NameError("błędna nazwa")
print(name)
```

#### Asercje
Asercje są kontrolą stanu jaki powinno się uzyskać po wykonaniu określonego fragmentu kodu testuje ona i jeśli wynik jest fałszywy to jest rzucany wyjątek
```Python
print(1)
assert 2 + 2 == 4
print(2)
assert 1 + 1 == 3
```
Asercje mogą również przyjmować drugi argument, który jest przekazywany, jeśli assercja zawiedzie
```Python
temp = -10
assert temp >= 0, "mniej niż 0"
```

> Gdy asercja się nie wykona poprawnie można wyłapać jej błąd używając bloku `try except`, jeśli to nie będzie zrobione program się zatrzyma:exclamation:

### Otwieranie plików
Operacje na plikach w Pythonie przed edycją pliku potrzeba go otworzyć przy pomocy poniższego polecenia
```Python
myfile = open("spam.txt")
```
> Argumentem funkcji `open` jest ścieżką do pliku. Jeśli plik znajduje się w katalogu projektu wystarczy wpisać jego nazwę :exclamation:

Pliki można otwierać i przetwarzać w różnych trybach. Tryb ustawia się przez podanie go jako drugi argument funkcji `open` podanie `r` umożliwia otwarcie pliku w trybie tylko do odczytu co zresztą jest trybem domyślnym.

Parametr | Opis
-------- | ---------
w | zapewnia tryb zapisu zawartości pliku (nadpisuje wcześniejszą zawartość lub tworzy plik, gdy nie istnieje)
a | zapewnia możliwość dopisywania do pliku bez utraty wcześniejszej jego zawartości
b | otwiera plik w trybie binarnym używane do plików innych niż tekstowe np. obrazy, dźwięk itp. 
```Python
myfile = open("spam.txt", "w")
myfile = open("spam.txt", "r")
myfile = open("spam.txt", "wb")
```
Odczytywanie pliku umożliwia metoda `read`. Po wykonaniu operacji na pliku obowiązkową czynnością będzie jego zamknięcie przy pomocy wywołania metody `close` wywołanej na rzecz obiektu pliku.
```Python
file = open("filename.txt", "r")
cont = file.read()
print(cont)
file.close()
```

Do odczytywania można użyć metody `read` wraz z parametrem, który informuje o tym, ile bajtów powinna być odczytana. Metoda ta możne być wykonywana kilka razy z kolei dla tego samego obiektu pliku, w celu odczytania z pliku bajt po bajcie. Wywołanie metody `read` bez argumentu odczyta pozostałe bajty pliku. Gdy zawartość pliku zostanie odczytana w całości kolejna próba odczytania zwróci pusty ciąg znaków.
```Python
file = open("filename.txt", "r")
print(file.read(10))
print(file.read(5))
print(file.read(6))
print(file.read())
file.close()
```
Do odczytania poszczególnych linii z pliku wykorzystuje się metodę `readlines` która zwraca listę, w której każdy element jest linią z odczytanego pliku.
```Python
file = open("filename.txt", "r")
print(file.readlines())
file.close()
```
Do odczytu z pliku linia po linii można również wykorzystać pętlę `for` 
```Python
file = open("filename.txt", "r")
for line in file:
    print(line)
file.close()
```
#### Zapisywanie plików
Do zapisywania plików wykorzystuję się metodę `write` zapisuje ona ciągi znaków do pliku.
```Python
file = open("newFile.txt", "w")
file.write("Ten tekst zostanie zapisany do pliku")
file.close()
```
Gdy plik otworzony jest w trybie zapisu istniejąca zawartość pliku zostanie usunięta co pokazuje poniższy fragment kodu.
```Python 
file = open("newFile2.txt", "r")
print("Odczyt zawartości domyślnej")
print(file.read())
print("Koniec")
file.close()

file = open("newFile2.txt", "w")
print(file.write("Jakiś tekst"))
file.close()

file = open("newFile2.txt", "r")
print("Odczyt zawartości domyślnej")
print(file.read())
print("Koniec")
file.close()
```
Jak można zauważyć metoda zapisująca informacje do pliku zwraca ilość zapisanych bajtów do pliku, jeśli zapis się powiedzie.

Dobrą praktyką jest upewnienie się, że pliki zostaną zamknięte po ich użyciu. Jednym ze sposobów na to jest użycie bloków `try` i `finally`.
```Python
try:
    f = open("fileName.txt")
    print(f.read())
finally:
    f.close()
```
> To zapewnia, że plik jest zawsze zamknięty, nawet jeśli wystąpi błąd:exclamation:

Alternatywą w pracy z plikiem jest użycie operatora `with`. Tworzy on tymczasową zmienną, która jest dostępna wyłącznie na poziomie wciętego bloku instrukcji `with`.
```Python
with open("filename.txt") as f:
    print(f.read())
```

> Plik zostanie automatycznie zamknięty po wyjściu z bloku `with` nawet jeśli błędy pojawią się w trakcie jego wykonywania:exclamation:



[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/sHG6yoe7)
# Język skryptowy lab3

### Tablice

 Tablice w Pythonie nie są takie jak tablice znane z Javy lub C ale bardziej przypominają listy.
 Tablica jest strukturą danych przechowującą wartości tego samego typu.
 Jest to główna różnica między tablicami i listami w pythonie.
 Aby móc używać tablic w pythonie trzeba zaimpotrować ze standardowych bibliotek pythona
 moduł `array` dlatego, że tablice w pythonie nie są uznawane za podstawowe typy danych jakimi są np watości
 całkowite czy ciągi znaków
 ```Python
from array import *
```
 Poniżej przedstawiono przykładową deklarację tablicy
```Python
 nazwa_tablicy = array(kod_typu_przechowywanych_danych, [inicjalizacja_wartościami])
```
Parametr (typ przechowywanych danych) | Opis
-------- | ---------
 b | Reprezentuje liczbę całkowitą ze znakiem o rozmiarze 1
 B | Reprezentuje liczbę całkowitą bez znaku o rozmiarze 1
 c | Reprezentuje znak wielkości 1 bajtu
 u | Reprezentuje znak Unicode o rozmiarze 2 bajty
 h | Reprezentuje liczbę całkowitą ze znakiem o rozmiarze 2 bajty
 H | Reprezentuje liczbę całkowitą bez znaku o rozmiarze 2 bajty
 i | Reprezentuje liczbę całkowitą ze znakiem o rozmiarze 2 bajty
 I | Reprezentuje liczbę całkowitą bez znaku o rozmiarze 2 bajty
 w | Reprezentuje znak Unicode o wielkości 4 bajty
 l | Reprezentuje liczbę całkowitą ze znakiem o rozmiarze 4 bajtów
 L | Reprezentuje liczbę całkowitą bez znaku o wielkości 4 bajty
 f | Reprezentuje zmiennoprzecinkowy rozmiar 4 bajtów
 d | Reprezentuje zmiennoprzecinkowy rozmiar 8 bajtów
 
 Pojedyncze elementy pobiera się przy pomocy odwołania do indeksu na którym znajduje się element, tablice indeksowane są od 0
```Python
from builtins import print

my_array = array('i', [1, 2, 3, 4, 5])
print(my_array[1])
print(my_array[2])
print(my_array[0])
print()

my_array = array('i', [1, 2, 3, 4, 5])
for i in my_array:
    print(i)
```
Dodawanie kolejnego indeksu do tablicy używając metody `append`
```Python
my_array = array('i', [1, 2, 3, 4, 5])
my_array.append(6)
```
Dodawanie kolejnego indeksu do tablicy używając metody `insert`. Metoda `insert` wstawia wartość na odpowiednim indexie w tablicy
```Python
my_array.insert(0, 0)
```
Wstawiana wartość umieszczana jest w odpowiednie miejsce w tablicy przesuwając dalszą część tablicy o jeden indeks.

W pythonie jest możliwość rozszerzania tablicy przez więcej niż jedną wartość przy użyciu metody `extend`
```Python
my_array = array('i', [1, 2, 3, 4, 5])
my_extend_array = array("i", [6, 7, 8, 9, 10])
my_array.extend(my_extend_array)
print(my_array)
```
Do tablicy można również dodawać elementy znajdujące się w liście przy użyciu metody `fromlist`
```Python
my_array = array('i', [1, 2, 3, 4, 5])
c = [11, 12, 13]
my_array.fromlist(c)
```
Usuwanie elementu z listy z użyciem metody `remove'
```Python
my_array = array('i', [1, 2, 3, 4, 5])
my_array.remove(4)
```
Usuwanie ostatniego elementu z tablicy metodą `pop`
```Python
my_array = array('i', [1, 2, 3, 4, 5])
my_array.pop()
```
Sprawdzenie elementu przy użyciu metody `index` zwraca pierwszy indeks elementu na którym znajduje się podana wartość
```Python
my_array = array('i', [1, 2, 3, 4, 5])
print(my_array.index(5))

my_array = array('i', [1, 2, 3, 3, 5])
print(my_array.index(3))
```
Użycie metody `reverse` powoduje odwrócenie tablicy na rzecz której została wywołana ta metoda
```Python
my_array = array('i', [1, 2, 3, 4, 5])
my_array.reverse()
print(my_array)
```
Możliwe jest też sprawdzenie pod jakim adresem w pamięci komputera znajduje się dana tablica oraz jaką ma długość
```Python
my_array = array('i', [1, 2, 3, 4, 5])
print(my_array.buffer_info())
```
Sprawdzanie liczby wystąpień danego element w tablicy
```Python
my_array = array('i', [1, 2, 3, 3, 5])
print(my_array.count(3))
```
Konwersja tablicy do łańcucha znaków
```Pythonmy_array1 = array('u', ['s', 'p', 'a', 'm'])
print(my_array1)
print(my_array1.tounicode())
```

```Python
word = "spam"
my_array = array(str('u'), [])
my_array.extend(list(word))
print(my_array.tounicode())
```
Konwersja tablicy do listy z użyciem metody `tolist`
```Python
my_array = array('i', [1, 2, 3, 4])
list = my_array.tolist()
```
Łączenie łańcuchów znaków z tablicą znaków z użyciem metody `fromstring`
```Python
my_array = array('u', ['s', 'p', 'a', 'm'])
my_array.extend(" egg")
print(my_array.tounicode())
```
### None
 Obiekt `None` jest używany do reprezentacji braku wartości, jest on podobny do `null'a` w innych językach programowania
 Tak jaki inne puste wartości jak np. 0, [] i pusty ciąg znaków, jest on fałszem gdy skonwertujemy go na wartość logiczną:
print("none")
print(bool(None))
print("None")

 Obiekt `None` jest zwracany przez funkcję gdy bezpośrednio nie zwraca ona niczego konkretnego.

### Słowniki
Słowniki są strukturą danych która służy do mapowania dowolnych kluczy na wartość. Słowniki mogą być indeksowane tak samo jak listy przy użyciu kwadratowych nawiasów zawierających klucz
```Python
ages = {"I": 78, "You": 20, "Him": 24}
print(ages["I"])
print(ages["Him"])
```
>Każdy element w słowniku reprezentowany jest przez parę `klucz:wartość`

Próba pobrania elementu używając klucza który nie istnieje w słowniku zwróci błąd `KeyError`.
```Python
colors = {
    "red": [255, 0, 0],
    "green": [0, 255, 0],
    "blue": [0, 0, 255]
}
print(colors["red"])
print(colors["yellow"])
print(colors["green"])
```
>Jak widać słowniki mogą przechowywać jako wartości dane dowolnych typów

Tylko niezmienne obiekty mogą być używane jako klucze dla słowników, czyli takie których nie można zmienić. Do tej pory jedynymi możliwymi do zmienienia poznanymi obiektami są listy i tablice.
Próba użycia zmiennego obiektu do słowa kluczowego powoduje błąd `TypeError`
```Python
 bad_dict = {[1, 2, 3]: "one two three", }
```
 Jak w listach klucze słownika mogą posiadać wartości różnych typów.
```Python
squares = {1: 1, 2: 4, 3: "spam", 4: 16}
squares[8] = 64
squares[3] = 9
squares[5] = 25
```
Do weryfikacji czy klucz znajduje się już w słowniku można wykorzystać operatory `in` i `not in` tak jak dla list.
```Python
nums = {1: "one",
        2: "two",
        3: "three"}
print(1 in nums)
print("three" in nums)
print(4 not in nums)
```
 Metoda `get` służy do pobierania elementów ze słownika. W przypadku gdy podany argument(klucz) nie zostanie znaleziony w słowniku
 metoda zwróci obiekt `None`
```Python
pairs = {
    "orange": [2, 3, 40], 0: "spam", True: False, None: "True", 2: "apple"}
print(pairs.get("orange"))
print(pairs.get(7))
print(pairs.get(2))
print(pairs.get(True))
print(pairs.get(1235, "not in dictionary"))
print(len(pairs))
```
 Odczytywanie danych ze słownika może odbywać się z wykorzystaniem metody `get`
```Python
for i in pairs:
    print(str(i) + "\t" + str(pairs.get(i)))
```
 lub odwołania przez podanie nazwy słownika i odpowiedniego klucza w nawiasach kwadratowych.
```Python
for i in pairs:
    print(i, pairs[i])
 oraz w krótszej konstrukcji
print()
print([(key, pairs[key]) for key in pairs])
```
#### Scalanie słowników
```Python
fish = {'name': "Nemo", 'hands': "fins", 'special': "gills"}
dog = {'name': "Clifford", 'hands': "paws", 'color': "red"}
 #Python 3.5+
fishdog = {**fish, **dog}
print(fishdog)

 #Python 2.x
from itertools import chain

print(dict(chain(fish.items(), dog.items())))
```
 Konstruktor `dict()` może być użyty do tworzenia słowników z argumentów będących kluczem z przypisana do niego wartością
 lub z pojedynczej iteracji par klucz-wartość lub z pojedynczego słownika i argumentów słów kluczowych
```Python
print(dict(a=1, b=2, c=3))
print(dict([('d', 4), ('e', 5), ('f', 6)]))
print(dict([('a', 1)], b=2, c=3))
print(dict({'a': 1, 'b': 2}, c=3))
```
 Krotki `Tuples` są podobne do list z wyjątkiem tego, że nie można ich zmieniać tworzy się je z wykorzystaniem nawiasów okrągłych
words = ("spam", "eggs", "saussages")
 Dostęp do elementu uzyskuje się przez podanie nazwy i numeru parametru objętego w nawiasy kwadratowe

 Próba podmiany któregoś elementu na inny skutkuje błędem `TypeError`. Krotki podobnie jak słowniki i listy mogą się nawzajem zagnieżdżać. Krotki można też tworzyć bez użycia nawiasów oddzielając wartości przecinkami.
```Python
my_tuple = "one", "two", "three"
print(my_tuple[0])
```
 Krotki są szybsze niż listy lecz nie można zmieniać ich zawartości
### Wycinki list
 Wycinki listy zapewniają bardziej zaawansowany sposób pobierania wartości z listy. Podstawowe krojenie list polega na
 indeksowaniu listy dwiema liczbami całkowitymi rozdzielonymi dwukropkami. Zwraca nową listę zawierającą wszystkie
 wartości ze starej listy między indeksami
```Python
squares = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
print(squares[2:6])
print(squares[3:8])
print(squares[0:1])
```
>Pierwszy indeks podany w zakresie wycinka listy jest zawarty w wyniku, ale drugi już nie jest

 Jeśli pominięto pierwszą liczbę w wycinku listy, uważa się ją za początek listy, jeśli pominięto drugą liczbę,
 uważa się, że jest ona końcem
```Python
squares = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
print(squares[:7])
print(squares[7:])
```
>Wycinanie można też wykonać na krotkach
  Wycinanie z list może się również odbywać z użyciem trzeciej liczby reprezentującej krok dla pobranych wartości z listy
```Python
squares = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
print(squares[::2])
print(squares[2:7:3])
```
 Zastosowanie kroku _-1_ spowoduje pobranie listy od jej końca

 Wzorce list są użytecznym sposobem szybkiego tworzenia list, których zawartość jest zgodna z prostą regułą
```Python
cubes = [i ** 3 for i in range(5)]
print(cubes)
```
 Wzorzec listy może również zawierać instrukcję `if`, która wymusi warunek na wartościach na liście
```Python
evens = [i ** 2 for i in range(10) if i ** 2 % 2 == 0]
print(evens)
```
### Przydatne metody dla łańcuchów znaków
:small_blue_diamond: join - dołącza listę ciągów do innego ciągu znaków jako separator
:small_blue_diamond: replace - zamienia jeden wycinek napisu innym
:small_blue_diamond: startswith and endswith - określa, czy istnieje podłańcuch odpowiednio na początku i na końcu łańcucha
:small_blue_diamond: lower upper - nazmiana napisów na małe i wielkie litery
:small_blue_diamond: split - działa podobnie do `join` z pewnym separatorem w liście
:small_blue_diamond: format - podstawia argumenty w ciągu znaków
```Python
print(",".join(["spam", "eggs", "spam"]))
print("Hello Me".replace("ME", "world"))
print("This is a sentence.".startswith("This"))
print("This is a sentence.".endswith("sentence"))
print("This is a sentence.".upper())
print("This is a sentence.".lower())
print("This is a sentence.".split(","))

nums = [4, 5, 6]
msg = "Numbers: {0} {1} {2}".format(nums[0], nums[1], nums[2])
print(msg)
print("{x},{y}".format(x=2, y=3))
```
 Często używane w instrukcjach warunkowych, funkcje `all` i `any` przyjmują listę jako argument  zwracają wartość `True`
 Jeśli odpowiednio wszystkie lub który kolwiek z jej argumentów ocenia się jako `True`.
 Funkcja `enumerate` może być użyta do iteracji przez wszystkie wartości i indeksy listy jednocześnie.
```Python
nums = [55, 44, 33, 22, 11]

if all([i > 5 for i in nums]):
    print("Wszystkie większe od 5")
if any([i % 2 == 0 for i in nums]):
    print("Przynajmniej jedna parzysta")

for v in enumerate(nums):
    print(v)



# Język skryptowy lab4

### Programowanie funkcyjne
Programowanie funkcyjne to styl programowania, który opiera się na funkcjach.
Kluczową częścią programowania funkcjonalnego są funkcje wyższego rzędu. 
Funkcje wyższego rzędu przyjmują inne funkcje jako argumenty lub zwracają je jako wyniki.
```Python
def apply_twice(func, arg):
    return func(func(arg))

def add_five(x):
    return x + 5

print(apply_twice(add_five, 10))
```
>Funkcja __apply_twice__ przyjmuje inną funkcję jako argument i wywołuje ją dwukrotnie wewnątrz.

### Czyste funkcje
Programowanie funkcyjne ma na celu wykorzystanie czystych funkcji. czyste funkcje nie mają skutków ubocznych i zwracają wartość, która zależy tylko od ich argumentów.
tak działają funkcje matematyczne: dla przykładu `cos (x)` dla tej samej wartości `x`, zawsze zwracają ten sam wynik
poniżej są przykłady funkcji czystych i nieczystych

czysta funkcja
```Python
def pure_function(x, y):
    temp = x + 2 * y
    return temp / (2 * x + y)
```
nieczysta funkcja 
```Python
some_list = []

def impure(arg):
    some_list.append(arg)
```
> Powyższa funkcja nie jest funkcją czystą ponieważ zmienia ona stan listy `some_list`

Używanie czystych funkcji ma zarówno zalety, jak i wady.
Czyste funkcje są:
- bardziej zrozumiałe;
- łatwiejsze w testowaniu;
- bardziej wydajne;
- łatwiejsze do uruchomienia równolegle.

### Wyrażenia Lambda
Tworzenie funkcji normalnie (za pomocą `def`) przypisuje ją do zmiennej automatycznie.
Różni się to od tworzenia innych obiektów (takich jak łańcuchy i liczby całkowite) które można tworzyć w locie, bez przypisywania ich do zmiennej.
To samo jest możliwe w przypadku funkcji, pod warunkiem, że są one tworzone przy użyciu wyrażenia __lambda__. Funkcje utworzone w ten sposób są znane jako anonimowe.
To podejście jest najczęściej używane podczas przekazywania prostej funkcji jako argumentu do innej funkcji. Składnia jest pokazana w następnym przykładzie i składa się ze słowa kluczowego `lambda`, po którym następuje lista argumentów, dwukropek i wyrażenie do wyznaczenia i do zwrotu.
```Python
def my_func(f, arg):
    return (f(arg))

print(my_func(lambda x: 2 * x * x, 5))
```
Funkcje lambda nie są tak potężne, jak nazwane funkcje.
Mogą tylko rzeczy, które wymagają pojedynczego wyrażenia - zwykle równoważne pojedynczemu wierszowi kodu.
```Python
# nzawana funkcja
def polynomial(x):
    return x ** 2 + 5 * x + 4

print(polynomial(-4))

# lambda
print((lambda x: x ** 2 + 5 * x + 4)(-4))
```
Funkcje lambda mogą być przypisane do zmiennych i używane jak normalne funkcje.
```Python
double = lambda x: x * 2
print(double(7))
```
>Jednak rzadko istnieje ku temu dobry powód - zazwyczaj lepiej jest zdefiniować funkcję z `def`

### Funkcje `map` i `filter`
Wbudowane funkcje `map` i `filter` są bardzo przydatnymi funkcjami wyższego rzędu, które działają na listach (lub innych "iterowalnych" obiektach).
Funkcja `map` przyjmuje funkcję i jest iterowalna jako argumenty i zwraca nową iterowalną z funkcją zastosowaną do każdego argumentu.
```Python
def add_five(x):
    return x + 5

nums = [11, 22, 33, 44, 55]
result = list(map(add_five, nums))
print(result)
```
Moglibyśmy osiągnąć ten sam wynik łatwiej dzięki składni lambda
```Python
nums = [11, 22, 33, 44, 55]

result = list(map(lambda x: x + 5, nums))
print(result)
```
>Aby przekonwertować wynik na listę, użyliśmy wyrażenia list

Funkcja `filter` jest iterowalna przez usunięcie elementów, które nie pasują do predykatu (funkcja zwracająca wartość logiczną).
```Python
nums = [11, 22, 33, 44, 55]
res = list(filter(lambda x: x % 2 == 0, nums))
print(res)
```
>Podobnie jak `map`, wynik musi zostać jawnie przekonwertowany na listę, jeśli chcesz ją wydrukować

### Generatory
Generatory są typem iterowalnym jak listy lub krotki.
W przeciwieństwie do list nie pozwalają na indeksowanie z dowolnymi indeksami, ale nadal mogą być iterowane za pomocą pętli `for`.
Można je utworzyć za pomocą funkcji i instrukcji `yield`
```Python
def countdown():
    i = 5
    while i > 0:
        yield i
        i -= 1
        
for i in countdown():
    print(i)
```
>Instrukcja `yield` służy do zdefiniowania generatora, zastępując powrót funkcji, aby dostarczyć wynik do wywołującego bez niszczenia lokalnych zmiennych.

Ze względu na to, że przetwarzają po jednym elemencie, generatory nie mają ograniczeń dotyczących list pamięci.
W rzeczywistości mogą być nieskończone!
```Python
def infinite_sevens():
    while True:
        yield 7

for i in infinite_sevens():
    print(i)
```
>W skrócie, generatory pozwalają zadeklarować funkcję, która zachowuje się jak iterator, tzn. może być użyta w pętli `for`

Generatory skończone można konwertować na listy, przekazując je jako argumenty funkcji listy
```Python 
def numbers(x):
    for i in range(x):
        if i % 2 == 0:
            yield i

print(list(numbers(11)))
```
>Używanie generatorów prowadzi do zwiększenia wydajności, co jest wynikiem leniwego (na żądanie) generowania wartości, co przekłada się na mniejsze zużycie pamięci. Ponadto nie musimy czekać, aż wszystkie elementy zostaną wygenerowane, zanim zaczniemy z nich korzystać

### Dekorator
Dekoratory umożliwiają modyfikowanie funkcji za pomocą innych funkcji.
Jest to idealne rozwiązanie, gdy potrzebujesz rozszerzyć funkcjonalność funkcji, których nie chcesz modyfikować
```Python
def decor(func):
    def wrap():
        print("==================")
        func()
        print("==================")
    return wrap

def print_text():
    print("Hello world!")

decorated = decor(print_text)
decorated()
```
Zdefiniowaliśmy funkcję o nazwie `decor`, która ma jeden parametr `func`. Wewnątrz dekoru zdefiniowaliśmy zagnieżdżoną funkcję o nazwie `wrap`.
Funkcja `wrap` wypisuje ciąg znaków, wywołuje `func()` i wypisuje kolejny ciąg znaków. Funkcja `decor` zwraca funkcję `wrap` jako jej wynik.
Można powiedzieć, że zmienna `decorated` to dekorowana wersja `print_text` - to `print_text` plus coś.
W rezultacie, jeśli napiszemy użytecznego dekoratora moglibyśmy chcieć zastąpić `print_text` całkowicie dekorowaną wersją, więc zawsze mamy naszą wersję `print_text` wzbogaconą o coś nowego.

Dostawcy Python wspierają opakowywanie funkcji w dekoratorze poprzez oczekiwanie na definicję funkcji za pomocą nazwy dekoratora i symbolu _@_.
Jeśli definiujemy funkcję, możemy ją ozdobić za pomocą symbolu _@_
```Python
@decor
def print_text2():
    print("Spam")

print_text2()
```
### Rekurencja
Jest to bardzo ważna koncepcja w programowaniu funkcyjnym. Podstawą rekurencji jest samoodniesienie przez wywoływanie siebie.
klasycznym przykładem rekurencji jest wyznaczanie silni.
```Python
def factorial(x):
    if x ==1:
        return 1
    else:
        return x*factorial(x-1)

print(factorial(5))
```
Rekurencja może być też pośrednia. Jedna funkcja wywołuje drugą która wywołuje pierwszą itd. Może się to zdarzyć w przypadku dowolnej liczby funkcji.
```Python
def is_even(x):
    if x == 0:
        return True
    else:
        return is_odd(x - 1)

def is_odd(x):
    return not is_even(x)

print(is_even(23))
print(is_odd(17))
```
### Zbiory
Zbiory są strukturami danych podobnymi do list lub słowników. Są tworzone przy użyciu nawiasów klamrowych lub przy pomocy funkcji `set`. Mają one pewne funkcjonalności jak listy, tj. sprawdzanie czy zawierają konkretny przedmiot.
```Python
num_set = {1, 2, 3, 4, 5}
world_set = set(["spam", "eggs"])

print(3 in num_set)
print("spam" not in world_set)
```
Zbiory różnią się od list na kilka sposobów, ale umożliwiają kilka operacji dozwolonych na listach, takich jak `len`.
Są nieuporządkowane, co oznacza, że nie można ich indeksować.
Nie mogą zawierać duplikatów elementów.
Ze względu na sposób ich przechowywania sprawdzenie czy element jest częścią zbioru, jest szybsze od sprawdzenia czy jest on częścią listy.
Zamiast użycia `append` do dodania do zbioru używa się metody `add`.
Metoda `remove` usuwa określony element ze zbioru, `pop` usuwa dowolny element.
```Python
nums = {1, 2, 1, 3, 4, 5, 1}
print(nums)
nums.add(-7)
nums.remove(3)
print(nums)
```
>Podstawowym zastosowaniem zbiorów jest testowanie występowania elementów i eliminację duplikatów

Zbiory można łączyć używając operatorów matematycznych:
- `|` suma zbiorów
- `&` część wspólna zbiorów
- `-` różnica zbiorów
- `^` różnica symetryczna

### Moduł `itertools`
Znajduje się w standardowej bibliotece Pythona i posiada pewne użyteczne funkcje w programowaniu funkcyjnym.

Wiele funkcji w module itertools które działają na iteracjach podobnie do `map` i `filter':
- `takewhile` - pobiera element z iteracji jeśli funkcja predykatu jest prawdziwa
- `accumulate` - zwraca bieżącą sumę wartości w iteracji
```Python
nums = list(accumulate(range(9)))
print(nums)
print(list(takewhile(lambda x: x <= 6, nums)))
```
W module `itertools` jest również wiele funkcji kombinatorycznych tj. `product` i `permutations`. Są one używane, gdy chcemy wykonać zadanie ze wszystkimi możliwymi kombinacjami niektórych elementów.
```Python
letters = ("A", "B", "C")
print(list(product(letters, range(3))))
print(list(permutations(letters)))
```




[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/1j6GWGW_)
# Język skryptowy lab5

### Programowanie obiektowe
Wcześniej zostały przeanalizowane dwa paradygmaty programowania - imperatywne (używając instrukcji, pętli i funkcji jako podprogramów) i funkcyjne (używając czystych funkcji, funkcji wyższego rzędu i rekursji).

Innym bardzo popularnym paradygmatem jest programowanie obiektowe (OOP).
Obiekty są tworzone za pomocą klas, które są w rzeczywistości centralnym punktem OOP.
Klasa opisuje, czym będzie obiekt, ale jest oddzielona od samego obiektu. Innymi słowy, klasa może być opisana jako projekt, opis lub definicja obiektu.
Możesz użyć tej samej klasy jako plan tworzenia wielu różnych obiektów.

Klasy są tworzone przy użyciu słowa kluczowego `class` i wciętych bloków, które zawierają metody klas (które są funkcjami).
Poniżej znajduje się przykład prostej klasy i jej obiektów.
```Python 
class Cat:
    def __init__(self, color, legs):
        self.color = color
        self.legs = legs


felix = Cat("ginger", 4)
rover = Cat("dog-colored", 4)
stumpy = Cat("brown", 3)

print(felix.color)
```
>Ten kod definiuje klasę o nazwie `Cat`, która ma dwa atrybuty: _color_ i _legs_.
Następnie klasa służy do tworzenia trzech oddzielnych obiektów (reprezentantów) tej klasy.

### `__init__`
Metoda `__init__` jest najważniejszą metodą w klasie.
Jest ona wywoływana, gdy tworzona jest instancja (obiekt) klasy, używając nazwy klasy jako funkcji.

Wszystkie metody muszą mieć `self` jako pierwszy parametr, chociaż nie jest on jawnie przekazywany, Python dodaje za ciebie argument `self` - nie trzeba go uwzględniać, gdy wywołuje się metode. W definicji metody self odnosi się do instancji wywołującej metodę.

Instancje klasy mają atrybuty, które są związanymi z nimi fragmentami danych.
W tym przykładzie instancje klasy `Cat` mają atrybuty _color_ i _legs_. Dostęp do nich można uzyskać, umieszczając kropkę i nazwę atrybutu po instancji.
W metodzie `__init__` można użyć `self.atrybut` do ustawienia początkowej wartości atrybutów instancji.

>W powyższym przykładzie metoda `__init__` pobiera dwa argumenty i przypisuje je do atrybutów obiektu. Metoda `__init__` jest konstruktorem klasy.

### Metody
Klasy mogą mieć zdefiniowane inne metody w celu dodania do nich funkcjonalności.
Należy pamiętać, że wszystkie metody muszą mieć `self` jako pierwszy parametr.
Dostęp do tych metod można uzyskać za pomocą taki sam sposób jak do atrybutów, czyli przy pomocy składni z kropką.
```Python
class Dog:
  def __init__(self, name, color):
    self.name = name
    self.color = color

  def bark(self):
    print("Woof!")

fido = Dog("Fido", "brown")
print(fido.name)
fido.bark()
```

Klasy mogą również posiadać atrybuty klas, utworzone przez przypisanie zmiennych w treści klasy. Dostęp do nich można uzyskać z instancji klasy lub samej klasy.
```Python
class Dog:
    legs = 4
    def __init__(self, name, color):
        self.name = name
        self.color = color
        
fido = Dog("Fido", "brown")
print(fido.legs)
print(Dog.legs)
```
>Atrybuty klas są wspólne dla wszystkich instancji klasy.

Próba dostępu do atrybutu instancji, który nie jest zdefiniowany, powoduje wystąpienie błędu `AttributeError`. Dotyczy to również wywołania niezdefiniowanej metody.
```Python
class Rectangle:
  def __init__(self, width, height):
    self.width = width
    self.height = height

rect = Rectangle(7, 8)
print(rect.color)
```
## Dziedziczenie
Dziedziczenie zapewnia sposób udostępniania funkcji między klasami.
Wyobraź sobie kilka klas, `Cat`, `Dog`, `Rabbit` i tak dalej. Chociaż mogą się różnić pod pewnymi względami (tylko pies może mieć taką metodę), prawdopodobnie będą podobne w innych (wszystkie mają atrybuty kolor i imię).
Podobieństwo to można wyrazić, czyniąc je wszystkie dziedziczącymi z superklasy `Animal`, która zawiera wspólną funkcjonalność.
Aby dziedziczyć klasę z innej klasy, umieść nazwę nadklasy w nawiasach po nazwie klasy.
```Python
class Animal:
    def __init__(self, name, color):
        self.name = name
        self.color = color

class Cat(Animal):
    def purr(self):
        print("Purr...")

class Dog(Animal):
    def bark(self):
        print("Woof!")

fido = Dog("Fido", "brown")
print(fido.color)
fido.bark()
```
Klasa, dziedzicząca z innej klasy nazywana jest podklasą.
Klasa po której dziedziczą inne klasy nazywana jest superklasą.
Jeśli klasa dziedziczy po innej z tymi samymi atrybutami lub metodami, nadpisuje je.
```Python
class Wolf:
    def __init__(self, name, color):
        self.name = name
        self.color = color

    def bark(self):
        print("Grr...")

class Dog(Wolf):
    def bark(self):
        print("Woof")

husky = Dog("Max", "grey")
husky.bark()
```
>W powyższym przykładzie `Wolf` jest superklasą, `Dog` jest podklasą.

Dziedziczenie może być również pośrednie. Jedna klasa może dziedziczyć od innej i ta klasa może dziedziczyć z trzeciej klasy.
```Python
class A:
    def method(self):
        print("A method")

class B(A):
    def another_method(self):
        print("B method")

class C(B):
    def third_method(self):
        print("C method")

c = C()
c.method()
c.another_method()
c.third_method()
```
>Jednak nie jest możliwe dziedziczenie w koło.

Funkcja _super_ jest użyteczną funkcją związaną z dziedziczeniem, która odnosi się do klasy nadrzędnej. Można jej użyć do znalezienia metody o określonej nazwie w nadklasie obiektu.
```Python
class A:
    def spam(self):
        print(1)

class B(A):
    def spam(self):
        print(2)
        super().spam()

B().spam()
```
>`super().spam()` wywołuje metodę `spam` z nadklasy.

### Magiczne metody
Magiczne metody są specjalnymi metodami, które mają podwójne podkreślenia na początku i na końcu ich nazw.

Jak dotąd jedynym, z którym się spotkaliśmy, jest `__init__`, ale jest jeszcze kilka innych.
Są używane do tworzenia funkcjonalności, które nie mogą być reprezentowane jako normalna metoda.

Jednym z ich powszechnych zastosowań jest przeciążanie operatorów.
Oznacza to zdefiniowanie operatorów dla niestandardowych klas, które pozwalają na użycie operatorów takich jak `+` i `*`.
Przykładową magiczną metodą jest `__add__` dla `+`.
```Python
class Vector2D:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):
        return Vector2D(self.x + other.x, self.y + other.y)

    def toStr(self):
        return self.x, self.y

first = Vector2D(5, 7)
second = Vector2D(3, 9)
result = first + second
print(result.toStr())
```
>Metoda `__add__` pozwala na zdefiniowanie niestandardowego zachowania operatora `+` w klasie.
Jak widać, dodaje odpowiednie atrybuty obiektów i zwraca nowy obiekt, zawierający wynik.
Po zdefiniowaniu można razem dodać dwa obiekty danej klasy.

Metoda | Operator
-------- | ---------
`__sub__` | -
`__mul__` | *
`__truediv__` | /
`__floordiv__` | //
`__mod__` | %
`__pow__` | **
`__and__` | &
`__xor__` | ^
`__or__` | \\|

Wyrażenie `x + y` jest tłumaczone na `x.__add__ (y)`.

```Python
class SpecialString:
    def __init__(self, cont):
        self.cont = cont

    def __truediv__(self, other):
        line = "=" * len(other.cont)
        return "\n".join([self.cont, line, other.cont])


spam = SpecialString("spam")
hello = SpecialString("Hello world!")
print(spam / hello)
```
Python dostarcza również magiczne metody do porównań.

Metoda | Operator
-------|-------
`__lt__` | <
`__le__` | <=
`__eq__` | ==
`__ne__` | !=
`__gt__` | >
`__ge__` | >=

Jeśli `__ne__` nie jest zaimplementowane, zwraca przeciwieństwo `__eq__`.
Pomiędzy innymi operatoramin nie ma żadnych innych relacji.
```Python
class SpecialString:
    def __init__(self, cont):
        self.cont = cont

    def __gt__(self, other):
        for index in range(len(other.cont) + 1):
            result = other.cont[:index] + ">" + self.cont
            result += ">" + other.cont[index:]
            print(result)

spam = SpecialString("spam")
eggs = SpecialString("eggs")
spam > eggs
```
>Jak widać, można zdefiniować dowolne niestandardowe zachowanie dla przeciążonych operatorów.

Istnieje kilka magicznych metod tworzenia klas, które działają jak kontenery.
`__len__` dla `len()`
`__getitem__` dla indeksowania
`__setitem__` dla przypisania do wartości indeksowanych
`__delitem__` do usuwania indeksowanych wartości
`__iter__` dla iteracji obiektów (np. dla pętli)
`__contains__` dla sprawdzenia zawierania

Istnieje wiele innych metod magicznych, takich jak `__call__` dla wywoływania obiektów jako funkcji i `__int__`, `__str__`, i tym podobne, do konwersji obiektów na typy wbudowane.
```Python
import random

class VagueList:
    def __init__(self, cont):
        self.cont = cont

    def __getitem__(self, index):
        return self.cont[index + random.randint(-1, 1)]

    def __len__(self):
        return random.randint(0, len(self.cont) * 2)

vague_list = VagueList(["A", "B", "C", "D", "E"])
print(len(vague_list))
print(len(vague_list))
print(vague_list[2])
print(vague_list[2])
```
>Funkcja `len()` klasy VagueListz ostała przesłonięta, aby zwrócić losową liczbę.
Funkcja indeksowania zwraca również losowy element z zakresul listy na podstawie wyrażenia.

### Cykl życia obiektów
Cykl życia obiektu składa się z jego tworzenia, manipulacji i destrukcji.

Pierwszym etapem cyklu życia obiektu jest definicja klasy, do której należy.
Następnym etapem jest tworzenie instancja danego typu, gdy wywoływana jest funkcja `__init__`. Pamięć jest przydzielona aby przechowywać utworzoną instancję. Tuż przed tym zdarzeniem wywoływana jest metoda `__new__` klasy. Jest ona przesłaniana tylko w specjalnych przypadkach.
Po tym zdarzeniu obiekt jest gotowy do użycia.
>Inny kod może następnie wchodzić w interakcję z obiektem, wywołując na nim funkcje i uzyskując dostęp do jego atrybutów.
W końcu zostanie wykorzystany i może zostać zniszczony.

Gdy obiekt zostanie zniszczony, pamięć przydzielona do niego zostanie zwolniona i może być wykorzystana do innych celów.
Zniszczenie obiektu następuje, gdy jego licznik odniesienia(referencji) osiągnie zero. Liczba referencyjna to liczba zmiennych i innych elementów odnoszących się do obiektu.
Jeśli nic nie odnosi się do obiektu (ma zerową wartość odniesienia), nic nie może z nim współdziałać, więc można go bezpiecznie usunąć.

W niektórych sytuacjach dwa (lub więcej) obiekty mogą być przywoływane tylko przez siebie, dlatego też można je usunąć.
Instrukcja __del__ zmniejsza liczbę odwołań obiektu o jeden, co często prowadzi do jego usunięcia.
Magiczną metodą jest `__del__`.
Liczba odwołań do obiektu wzrasta, gdy jest przypisana nowa nazwa lub umieszczona w kontenerze (liście, krotce lub słowniku). Liczba odwołań obiektu zmniejsza się, gdy zostanie usunięta za pomocą metody `__del__`, odniesienie zostanie ponownie przypisane lub jego odwołanie wykracza poza zakres. Kiedy licznik odwołań do obiektu osiąga zero, Python automatycznie go usuwa.

### Ukrywanie danych - enkapsulacja
Kluczową częścią programowania obiektowego jest enkapsulacja, która polega na pakowaniu powiązanych zmiennych i funkcji w pojedynczy, łatwy w użyciu obiekt - instancję klasy.
Powiązaną koncepcją jest ukrywanie danych, które stwierdza, że szczegóły implementacji klasy powinny być ukryte, a dla tych, którzy chcą korzystać z klasy, prezentowany jest czysty standardowy interfejs.
W innych językach programowania zwykle odbywa się to za pomocą prywatnych metod i atrybutów, które blokują zewnętrzny dostęp do określonych metod i atrybutów w klasie.

Filozofia Pythona jest nieco inna. Często jest to określone jako "wszyscy tutaj jesteśmy dorośli", co oznacza, że nie powinno się nakładać arbitralnie ograniczeń dostępu do części klasy. Dlatego nie ma sposobów na wymuszenie aby metoda lub atrybut, był ściśle prywatny.

>Istnieją jednak sposoby zniechęcenia ludzi do uzyskiwania dostępu do części klasy, na przykład poprzez oznaczenie, że jest to szczegół implementacji i będą one używane na własne ryzyko.

Słabo prywatne metody i atrybuty mają na początku jedno podkreślenie.
Oznacza to, że są one prywatne i nie powinny być używane przez zewnętrzny kod. Jednak jest to głównie konwencja i nie blokuje dostępu do kodu zewnętrznego.
Jego jedynym faktycznym skutkiem jest to, że `from module_name import *` nie importuje zmiennych rozpoczynających się od pojedynczego podkreślenia.
```Python
class Queue:
    def __init__(self, contents):
        self._hiddenlist = list(contents)

    def push(self, value):
        self._hiddenlist.insert(0, value)

    def pop(self):
        return self._hiddenlist.pop(-1)

    def __repr__(self):
        return "Queue({})".format(self._hiddenlist)

queue = Queue([1, 2, 3])
print(queue)
queue.push(0)
print(queue)
queue.pop()
print(queue)
print(queue._hiddenlist)
```
>W powyższym kodzie atrybut _hiddenlist jest oznaczony jako prywatny, ale wciąż można uzyskać do niego dostęp w kodzie zewnętrznym.
Metoda magiczna __repr__ jest używana do reprezentacji ciągów instancji.

Silnie prywatne metody i atrybuty mają __podwójne podkreślenie__ na początku ich nazw. To powoduje, że ich nazwy są zniekształcone, co oznacza, że nie można uzyskać do nich dostępu spoza klasy.
Celem tego nie jest zapewnienie, że są one prywatne, ale unikanie błędów, gdy istnieją podklasy, które mają metody lub atrybuty o tych samych nazwach.

Zniekształcone nazwy metod mogą być nadal dostępne zewnętrznie, ale pod inną nazwą. Metoda `__privatemethod` klasy `Spam` może być dostępna zewnętrznie poprzez `_Spam__privatemethod`.
```Python
class Spam:
    __egg = 7

    def print_egg(self):
        print(self.__egg)

s = Spam()
s.print_egg()
print(s._Spam__egg)
print(s.__egg)
```
>Zasadniczo Python chroni metody i atrybuty, przez wewnętrzne zmiany nazw, aby zawierały nazwę klasy.

### Metody klas
Metody obiektów, które przyjrzeliśmy się do tej pory, są wywoływane przez instancję klasy, która jest następnie przekazywana do parametru ___self___ metody.
Metody klas są różne - są wywoływane przez klasę, która jest przekazywana do parametru ___cls___ metody.
Powszechnym ich zastosowaniem są metody wytwórcze, które tworzą instancję klasy, używając innych parametrów niż te zwykle przekazywane do konstruktora klasy.
Metody klas są oznaczone adnotacją ___classmethod___.
```Python
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def calculate_area(self):
        return self.width * self.height

    @classmethod
    def new_square(cls, side_length):
        return cls(side_length, side_length)

square = Rectangle.new_square(5)
print(square.calculate_area())
```
___new_square___ jest metodą klasy i jest wywoływany w klasie, a nie w instancji klasy. Zwraca nowy obiekt klasy ___cls___.

>Technicznie, parametry `self` i `cls` są po prostu konwencjami; można je zmienić na cokolwiek innego. Są one jednak powszechnie stosowane, więc rozsądnie jest trzymać się ich używania.

### Metody statyczne
Metody statyczne są podobne do metod klasowych, z tym wyjątkiem, że nie otrzymują żadnych dodatkowych argumentów; są one identyczne z normalnymi funkcjami należącymi do klasy.
Są one oznaczone adnotacją ___staticmethod___.
```Python
class Pizza:
    def __init__(self, toppings):
        self.toppings = toppings

    @staticmethod
    def validate_topping(topping):
        if topping == "pineapple":
            raise ValueError("No pineapples!")
        else:
            return True

ingredients = ["cheese", "onions", "spam"]
if all(Pizza.validate_topping(i) for i in ingredients):
    pizza = Pizza(ingredients)
```

### Właściwości
Właściwości zapewniają sposób dostosowywania dostępu do atrybutów instancji.
Są one tworzone przez umieszczenie adnotacji ___property___ nad metodą, co oznacza, że gdy zostanie wywołany atrybut instancji o tej samej nazwie co metoda, metoda zostanie wywołana.
Jednym z typowych zastosowań właściwości jest ustawienie atrybutu jako atrybutu "tylko do odczytu".
```Python
class Pizza:
    def __init__(self, toppings):
        self.toppings = toppings

    @property
    def pineapple_allowed(self):
        return False


pizza = Pizza(["cheese", "tomato"])
print(pizza.pineapple_allowed)
pizza.pineapple_allowed = True
```



[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/r4phpxNE)
# Lab6 - Wizualizacja danych - matplotlib.

## Wprowadzenie do pyplot`a
`matplotlib.pyplot` jest zbiorem funkcji, które sprawiają, że `matplotlib` działa jak MATLAB. Każda funkcja `pyplot` dokonuje jakiejś
zmiany w figurze: np. tworzy figurę, tworzy obszar wykreślania w figurze, wykreśla jakieś linie w obszarze wykreślania, dekoruje
wykres etykietami, itp.
W `matplotlib.pyplot` różne stany są zachowywane przez wywołania funkcji, więc śledzi takie rzeczy jak bieżąca figura i obszar
kreślenia, a funkcje kreślenia są kierowane do bieżących osi (proszę zauważyć, że "osie" tutaj i w większości miejsc w dokumentacji
odnosi się do części osiowej figury, a nie ścisłego terminu matematycznego dla więcej niż jednej osi).
Generowanie wizualizacji za pomocą `pyplot` jest bardzo szybkie:

```python
import matplotlib.pyplot as plt
plt.plot([1, 2, 3, 4])
plt.ylabel('etykieta osi Y')
plt.xlabel('etykieta osi X')
plt.show()
```
![image](https://github.com/kosa1010/PyLab6/assets/12736759/b9eed2f8-6cf4-46f6-b5b3-65b1a6cfea15)

### Dlaczego oś x ma zakres od 0-3, a oś y od 1-4?
Jeśli podasz pojedynczą listę lub tablicę do wykreślenia, matplotlib zakłada, że jest to sekwencja wartości `y` i automatycznie generuje
dla Ciebie wartości `x`. Ponieważ zakresy Pythona zaczynają się od 0, domyślny wektor `x` ma taką samą długość jak `y`, ale zaczyna się
od 0. Stąd wartości `x` to `[0, 1, 2, 3]`.
`Plot` jest uniwersalną funkcją i przyjmuje dowolną liczbę argumentów. Na przykład, aby wykreślić `x` względem `y`, można napisać:
```python
plt.plot([1, 2, 3, 4], [1, 4, 9, 16])
plt.show()
```

## Formatowanie stylu wykresu
Dla każdej pary argumentów `x`, `y` istnieje opcjonalny trzeci argument, który jest łańcuchem formatu wskazującym kolor i typ linii
wykresu. Litery i symbole łańcucha formatu pochodzą z MATLABa, i łączy się łańcuch koloru z łańcuchem stylu linii. Domyślnym
łańcuchem formatu jest '`b-`', który jest niebieską linią ciągłą. Na przykład, aby wykreślić wcześniejszy wykres używając czerwonych
punktów, należy wydać polecenie
```python
plt.plot([1, 2, 3, 4], [1, 4, 9, 16], 'r.')
plt.axis([0, 6, 0, 20])
plt.show()
```

Pełna lista stylów linii i łańcuchów formatowych znajduje się w dokumentacji polecenia plot:
https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.plot.html#matplotlib.pyplot.plot. Funkcja `axis` w powyższym
przykładzie przyjmuje listę `[xmin, xmax, ymin, ymax]` i określa zakresy wartości przedstawiane na osiach.
Gdyby `matplotlib` był ograniczony do pracy z listami, byłby dość bezużyteczny do przetwarzania liczb. W rzeczywistości wszystkie
sekwencje są wewnętrznie konwertowane na tablice `numpy`. Poniższy przykład ilustruje wykreślanie kilku linii o różnych stylach
formatowania w jednym wywołaniu funkcji przy użyciu tablic.
```python
import numpy as np
import matplotlib.pyplot as plt

# równomiernie próbkowany czas w odstępach 200ms
t = np.arange(0., 5., 0.2)

# czerwone kreski, niebieskie kwadraty i zielone trójkąty
plt.plot(t, t, 'r--', t, t**2, 'bs', t,t**3,'g^')
plt.show()
```
![image](https://github.com/kosa1010/PyLab6/assets/12736759/5a2f24d1-692a-4888-8ad7-64b34606a4ba)


Rysowanie kilku wykresów w jednym obszarze roboczym może odbywać się przez
- wielokrotne użycie funkcji `plot`
```python
y1 = [2, 4, 6]
plt.plot(x, y1, 'bo')
plt.plot(x, [value * 3 for value in y1], 'go')
plt.show()
```
- `x` i/lub `y` są tablicami 2D, wtedy dla każdej kolumny zostanie narysowany osobny zestaw danych
```python
x = [1, 2, 3]
y = np.array([[1,2],[3,4],[5,6]])
plt.plot(x, y)
plt.show()
```
```python
x = [1, 2, 3]
y = np.array([[1, 2], [3, 4], [5, 6]])
for col in range(y.shape[1]):
    plt.plot(x, y[:, col])
plt.show()
```
- określenie wielu zestawów składających się z współrzędnych `[x]`, `y` oraz z stringa definiującego kolor i styl linii [fmt]:
```python
x = [1, 2, 3]
y1 = [2, 4, 6]
plt.plot(x, y1, 'bo', x, [value * 3 for value in y1], 'go')
plt.show()
```
Dodatkowo dla serii danych można parametry tj. szerokość linii, etykietę legendy i inne
```python
plt.plot([1, 2, 3], [1, 2, 3], 'go-', label='line 1', linewidth=4)
plt.plot([1, 2, 3], [1, 4, 9], 'md:', label='line 2', markersize=15)
plt.legend()
plt.show()
```
Więcej informacji dotyczących legend pod adresem https://matplotlib.org/stable/tutorials/intermediate/legend_guide.html#sphxglr-tutorials-intermediate-legend-guide-py

## Praca z wieloma figurami i osiami
MATLAB, oraz `pyplot`, umożliwiają wykorzystanie bieżącego obszaru roboczego do rysowania wykresów względem osi (jeden pod
drugim lub obok drugiego). Wszystkie funkcje kreślenia odnoszą się do bieżących osi. Funkcja `gca` zwraca bieżące osie (instancja
`matplotlib.axes.Axes`), a `gcf` zwraca bieżącą figurę (instancja `matplotlib.figure.Figure`). Normalnie nie musisz się tym przejmować,
ponieważ wszystko jest załatwiane w tle. Poniżej znajduje się skrypt tworzący dwa podwykresy.
```python
def f(t):
    return np.exp(t) * np.cos(2*np.pi*t)

t1 = np.arange(0.0, 5.0, 0.15)
t2 = np.arange(0.0, 5.0, 0.01)

plt.figure()
plt.subplot(211)
plt.plot(t1, f(t1), 'bo', t2, f(t2), 'k')

plt.subplot(212)
plt.plot(t2, np.cos(2*np.pi*t2), 'r--')
plt.show()
```
![image](https://github.com/kosa1010/PyLab6/assets/12736759/322f3eda-d287-4ef9-b35e-860effb9f875)

Wywołanie funkcji `figure` jest opcjonalne, ponieważ figura zostanie utworzona, jeśli nie istnieje, tak samo jak oś zostanie utworzona
(odpowiednik jawnego wywołania `subplot()`), jeśli nie istnieje. Wywołanie `subplot` określa `numrows, numcols, plot_number,` gdzie
`plot_number` mieści się w zakresie od `1` do `numrows*numcols`. Przecinki w wywołaniu `subplot` są opcjonalne, jeśli
`numrows*numcols<10`. Zatem `subplot(211)` da taki sam rezultat jak `subplot(2, 1, 1)`.
Możesz stworzyć dowolną liczbę podwykresów i osi. Jeśli chcesz umieścić oś ręcznie, tj. nie na siatce prostokątnej, użyj `axes`, który
pozwala określić położenie jako `axes([left, bottom, width, height])`, gdzie wszystkie wartości są we współrzędnych ułamkowych (0
do 1).

Przykład ręcznego umieszczania osi https://matplotlib.org/stable/_downloads/fbec90da3a9f58258ab121e0d2037693/axes_demo.py

Przykład z dużą ilością podwykresów https://matplotlib.org/stable/gallery/subplots_axes_and_figures/subplots_demo.html

## Inne typy wykresów
### Kołowy
```python
import matplotlib.pyplot as plt

# Wykres kołowy, w którym plasterki będą uporządkowane i wykreślone w kierunku przeciwnym do ruchu wskazówek zegara:
labels = 'Frogs', 'Hogs', 'Dogs', 'Logs'
sizes = [15, 30, 45, 10]
explode = (0, 0.1, 0, 0) # wyeksponowany tylko drugi plaster (tj. "Hogs")

fig1, ax1 = plt.subplots()
ax1.pie(sizes, explode=explode, labels=labels, autopct='%1.1f%%', shadow=True, startangle=90)
ax1.axis('equal') # Równe proporcje zapewniają, że wykres jest rysowany jako okrąg.

plt.show()
```
Inne warianty wykresów kołowych dostępne pod adresem https://matplotlib.org/stable/gallery/pie_and_polar_charts/index.html

### Słupkowy
```python
import matplotlib.pyplot as plt

fig, ax = plt.subplots()

fruits = ['apple', 'blueberry', 'cherry', 'orange']
counts = [40, 100, 30, 55]
bar_labels = ['red', 'blue', '_red', 'orange']
bar_colors = ['tab:red', 'tab:blue', 'tab:red', 'tab:orange']

ax.bar(fruits, counts, label=bar_labels, color=bar_colors)

ax.set_ylabel('fruit supply')
ax.set_title('Fruit supply by kind and color')
ax.legend(title='Fruit color')

plt.show()
```
Inne warianty wykresów słupkowych i liniowych: https://matplotlib.org/stable/gallery/lines_bars_and_markers/index.html

### Wykres 3D
```python
import matplotlib.pyplot as plt
import numpy as np

ax = plt.axes(projection="3d")
u = np.linspace(0, 2 * np.pi, 100)
v = np.linspace(0, np.pi, 100)
r = 10
x = r * np.outer(np.cos(u), np.sin(v))
y = r * np.outer(np.sin(u), np.sin(v))
z = r * np.outer(np.ones(np.size(u)), np.cos(v))

ax.plot_surface(x, y, z, rstride=5, cstride=5, cmap=plt.cm.coolwarm)
plt.show()
```

Inne warianty wykresów 3D: https://matplotlib.org/stable/gallery/lines_bars_and_markers/index.html

