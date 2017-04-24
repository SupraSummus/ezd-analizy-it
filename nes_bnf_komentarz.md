<meta http-equiv='Content-Type' content='text/html; charset=utf-8' />

<h2>
<p align="center">Zapis propozycji nowej budowy metadanych<br/>
Niezbędnych Elementów Struktury (NES )<br/>
dokumentów elektronicznych,<br/>
w Notacji Backusa-Naura (BNF)</p>
</h2>

<p align="right"><em>Na skróty: dokument HTML jest tu: <a href="https://stas53.github.io/tests/nes_bnf.html"> nes_bnf.html</a>
</em></p>

### Środowisko

Rozporządzenie Ministra Spraw Wewnętrznych i Administracji
[z dnia 30 października 2006 r.](http://isap.sejm.gov.pl/DetailsServlet?id=WDU20062061517) określa niezbędne elementy struktury
(<em>NES</em>) dokumentów elektronicznych powstałych i gromadzonych w organach państwowych, państwowych jednostkach organizacyjnych,
w organach jednostek samorządu terytorialnego i samorządowych jednostkach organizacyjnych.<br/>
Stanowi ono, że każdy dokument elektroniczny powinien być opatrzony pewnymi metadanymi takimi jak identyfikator, twórca, tytuł,
data, format, zasady dostępu itd.

Z kolei, Rozporządzenie Ministra Spraw Wewnętrnych i Administracji
[z dnia 2 listopada 2006 r.](http://isap.sejm.gov.pl/DetailsServlet?id=WDU20062061519) w sprawie wymagań technicznych formatów zapisu
i informatycznych nośników danych, na których utrwalono materiały archiwalne przekazywane do archiwów państwowych, określło format
całej paczki danych (tzw. „paczki archiwalnej”), który powinien być stosowany przy przekazywaniu danych z urzędów do Archiwów Państwowych.
W szczególności, w Załączniku do Rozporządzenia został określony konkretny format plików XML, który należy zastosować przy eksporcie
metadanych. Format ten zdefiniowano formalnie przy pomocy tzw. XSD, czyli pliku definicji formatów XML.

### Propozycja zmian NES

Grupa robocza powołana w końcu 2016 roku przez porozumienie MC - NSA - PUW, przy współpracy osób z MKiDN, NDAP i Laboratorium EE,
przygotowała opis zmodyfikowanej wersji NES, dla potrzeb „paczki administracyjnej” — formatu danych przewidzianego do przekazywania
danych o sprawach z systemów EZD urzędów państwowych, do Sądów Administracyjnych.<br/>
Wydaje się, że po pewnych rozszerzeniach, ten sam format będzie mógł być wykorzystany do tworzenia „paczek migracyjnych” — do
przekazywania danych pomiędzy systemami EZD.

Dokument źródłowy przygotowany przez Grupę Roboczą [dostępny tu](http://epuap.gov.pl/wps/PA_E2_PI/zalacznik_oi/zalacznik_oi_1460_1)
jest obszernym materiałem tekstowym (.docx), zawierającym opisy poszczególnych metadanych oraz przykłady ich użycia.

### Zapis w notacji BNF

Dla umożliwienia szybkiego i wygodnego przeglądania proponowanej nowej budowy NES, zaproponowaliśmy zapisanie struktury metadanych
w postaci schematów produkcji, uzywanych do definiowania
[języków bezkontekstowych](http://edu.pjwstk.edu.pl/wyklady/jfa/scb/jfa-main-node11.html), w zapisie znanym jako
Notacja Backusa-Naura — BNF.

Dokument
[nes_bnf.html](https://stas53.github.io/tests/nes_bnf.html)
pokazuje zarówno strukturę danych, jak i ich zapis w tekstowym formacie XML.<br/>
Na stronie znajduje się dodatkowy przycisk, aktywuący wyświetlenie objaśnień.

