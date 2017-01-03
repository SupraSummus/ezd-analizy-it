Wykorzystanie formatu paczki archiwalnej jako formatu danych EZD
================================================================

Wstęp
-----

W tym dokumencie opisana jest propozycja użycia tzw. formatu paczki
archiwalnej [#paczka_archiwalna]_ jako głównego `formatu danych EZD`_.

W dokumencie używane są aliasy:

* "FPA" oznacza "format paczki archiwalnej"
* "FD EZD" oznacza "format danych EZD"

Zarys
-----

Elementami metryki sprawy są pojedyncze dokumenty XML, każdy w FPA.
Treść pism przechowywana jest w oddzielnym miejscu (nazwijmy je
"skład pism"). Elementy metryki mogą zawierać odniesienia do pism.

Aby takie rozwiązanie było poprawne niezbędne są zmiany w FPA lub w
FD EZD. Nie wszystkie zmiany podane poniżej są niezbędne.

Wskazanie elementu poprzedniego metryki
---------------------------------------

W FD EZD poprzedni element wskazywany jest z użyciem URI. W FPA nie
występuje wskazanie elementu poprzedniego jako specjalne pole do tego
przeznaczone. W FPA jest możliwość tworzenia relacji między dokumentami.

W FPA można zrealizować wskazanie poprzedniego elementu metryki za
pomocą relacji odpowiedniego typu. Takie rozwiązanie nie jest dobre,
ponieważ trudno wymusić dokładnie jedno wskazanie poprzedniego elementu
metryki.

W FPA można dodać pole wskazujące poprzedni element metryki.

Wskazanie wykonawcy czynności
-----------------------------

W FD EZD wykonawca czynności jest wskazywany za pomocą URI, w FPA za
pomocą pola :code:`tworca` typu :code:`Tworca`. Złożony typ
:code:`Tworca` zawiera pole :code:`id` typu :code:`Id` (niepusty napis).

W FD EZD można dopuścić wskazanie wykonawcy czynności za pomocą elementu
typu :code:`Twórca`.

W FPA można załączać URI wykonawcy w polu :code:`id` pola :code:`tworca`
lub wskazywać wykonawcę jako URI (np. jako odnośnik do części tego
samego dokumentu).

Specyfikacja czynności
----------------------

W FD EZD specyfikacja czynności jest polimorficznym polem. W FPA na
specyfikację czynności składa się wiele pól. Dużo pól określa metadane,
a zatem zmiana (także nadanie) metadanych jest reprezentowane przez
stworzenie dokumentu z odpowiednimi wartościami tych pól. W polu
:code:`relacja` występuje typ wyliczeniowy, którego niektóre wartości
odpowiadają akcjom (np. :code:`jestDekretacja`, :code:`jestWersja`).

Można specyfikacje czynności w FPA zostawić w postaci obecnej.

Lepszym rozwiązaniem jest zmiana struktury FPA. Należy dodać pole
"akcja", które będzie polimorficzne. Pola reprezentujące metadane
zostaną usunięte z korzenia i dodane w wariancie pola "akcja"
reprezentującym zmianę metadanych. Z typu wyliczeniowego, określającego
rodzaj relacji, zostaną usunięte wartości reprezentujące akcje.

Powiązania
----------

W FD EZD powiązania są listą URI. W FPA występuje pole 'relacja', które
oprócz odnośnika zawiera także pole wyliczeniowe typu relacji.

Z FPA należy usunąć niektóre typy relacji. Duża część typów występuje w
dwóch, symetrycznych wariantach (np. :code:`maCzesc`-:code:`jestCzescia`,
:code:`wymaga`-:code:`jestWymagany`). Taka konstrukcja powoduje
redundancję lub możliwość zapisania tej samej relacji na wiele sposobów.
Oprócz tego, jeśli decydujemy się na użycie blockchain'a, dokumenty po
utworzeniu muszą być niezmieniane. Uniemożliwia to zastosowanie relacji,
które prowadzą z dokumentu starszego (w nim są zdefiniowane) do
młodszego.

Do FPA należy dodać sposób wskazywania pism, które znajdują się w
składzie pism (nie są elementami metryki sprawy). FPA zapisuje
identyfikatory docelowych dokumentów jako trójki
(typ, wartość, podmiot), gdzie typ i wartość są napisami. Taki sposób
prawdopodobnie pozwoli na adresowanie obiektów niebędących elementami
metryki sprawy.

.. [#paczka_archiwalna]
   Plik schematu paczki `Metadane-1.7.xsd` jest dostępny pod adresem
   https://ade.ap.gov.pl/ndap-walidator/downloadmeta.do.
.. _`formatu danych EZD`: format-danych-ezd.rst
