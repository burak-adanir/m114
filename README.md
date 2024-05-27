# Modul 114: Daten Komprimieren Aufgaben

## Inhaltsverzeichnis

1. [Tag 2 Aufgaben](#tag-2-aufgaben)
   1. [Aufgabe 1: Baumstrukturen in der IT und Unterschiede zwischen binären und nicht-binären Bäumen](#aufgabe-1-baumstrukturen-in-der-it-und-unterschiede-zwischen-binären-und-nicht-binären-bäumen)
   2. [Aufgabe 2: Huffman-Algorithmus](#aufgabe-2-huffman-algorithmus)
   3. [Aufgabe 3: RLC für Farbbilder](#aufgabe-3-rlc-für-farbbilder)
   4. [Aufgabe 4: Dekodierung des RL-Codes](#aufgabe-4-dekodierung-des-rl-codes)
   5. [Aufgabe 5: LZW-Verfahren](#aufgabe-5-lzw-verfahren)
   6. [Aufgabe 6: BWT-Verfahren](#aufgabe-6-bwt-verfahren)
   7. [Aufgabe 7: ZIP-Komprimierung](#aufgabe-7-zip-komprimierung)
   8. [Aufgabe 8: Verlustlose Komprimierung](#aufgabe-8-verlustlose-komprimierung)
2. [Tag 1 Aufgaben](#tag-1-aufgaben)
   1. [Umwandlungstabellen und Binärrechnung](#umwandlungstabellen-und-binärrechnung)
      1. [Aufgabe 1: Umwandlungstabellen](#aufgabe-1-umwandlungstabellen)
      2. [Aufgabe 2: Umwandlung von Dezimal in Binär](#aufgabe-2-umwandlung-von-dezimal-in-binär)
      3. [Aufgabe 3: Umwandlung von Binär in Dezimal](#aufgabe-3-umwandlung-von-binär-in-dezimal)
      4. [Aufgabe 4: Umwandlung von Binär in Hexadezimal](#aufgabe-4-umwandlung-von-binär-in-hexadezimal)
      5. [Aufgabe 5: Addition von binären Zahlen](#aufgabe-5-addition-von-binären-zahlen)

## Tag 2 Aufgaben

### Aufgabe 1: Baumstrukturen in der IT und Unterschiede zwischen binären und nicht-binären Bäumen

Baumstrukturen finden in vielen Bereichen der IT Anwendung, unter anderem:

- **Dateisysteme:** Verzeichnisse und Dateien werden in einer Baumstruktur organisiert.
- **Datenbanken:** Datenbankindizes nutzen oft Baumstrukturen wie B-Bäume oder B+-Bäume.
- **Compiler:** Syntaxbäume (Parse Trees) werden verwendet, um die Struktur eines Programmcodes darzustellen.
- **Suchalgorithmen:** AVL-Bäume, Rote-Schwarze-Bäume und andere ausgeglichene Bäume werden verwendet, um die Effizienz von Suchoperationen zu verbessern.

Ein **binärer Baum** ist eine spezielle Art von Baumstruktur, bei dem jeder Knoten maximal zwei Kinder hat. Im Gegensatz dazu kann ein **nicht-binärer Baum** mehr als zwei Kinder pro Knoten haben.

### Aufgabe 2: Huffman-Algorithmus

Hier ist ein Beispiel zur Erstellung des Huffman-Codes:

1. **Wort wählen:** "INFORMATIONTECH"

2. **Häufigkeit der Buchstaben ermitteln:**

   | Buchstabe | Häufigkeit |
   |-----------|------------|
   | I         | 2          |
   | N         | 2          |
   | F         | 1          |
   | O         | 2          |
   | R         | 1          |
   | M         | 1          |
   | A         | 1          |
   | T         | 2          |
   | E         | 1          |
   | C         | 1          |
   | H         | 1          |

3. **Huffman-Baum erstellen:** Hier wird der Baum aufgebaut, indem die Knoten basierend auf den Häufigkeiten zusammengeführt werden.

4. **Codetabelle erstellen:**

   | Buchstabe | Huffman-Code |
   |-----------|---------------|
   | I         | 00            |
   | N         | 01            |
   | F         | 1000          |
   | O         | 1001          |
   | R         | 1010          |
   | M         | 1011          |
   | A         | 1100          |
   | T         | 1101          |
   | E         | 1110          |
   | C         | 11110         |
   | H         | 11111         |

5. **Wort in Binärcode umwandeln:** "INFORMATIONTECH" → 00 01 1001 1000 1010 00 1100 1101 00 1101 1110 11110 11111

6. **Partnerarbeit:** Der Partner würde dann die Tabelle und den Code verwenden, um das Wort zu dekomprimieren und die Richtigkeit zu überprüfen.

### Aufgabe 3: RLC für Farbbilder

Für ein quadratisches Bild mit 20 Pixel Kantenlänge:
- **Bitbreite:** Da das Bild 20x20 = 400 Pixel hat, reicht eine Bitbreite von 9 Bit (512 Werte) aus, um Wiederholungen zu codieren.
- **Einfarbiges Bild:** Wenn das Bild nur aus einer Farbe besteht, wird der RLC-Code sehr einfach sein, z.B. "400xFarbe".

### Aufgabe 4: Dekodierung des RL-Codes

Der RL-Code: `010100011110010010010010010010010010010110010110010010010010010010010010010001` für eine 8x8 Schwarz-Weiß-Rastergrafik wird wie folgt dekodiert:

1. Splitte den Code in Segmente mit Wiederholungen bis maximal 7:

   | Segment  | Farbe  | Wiederholung |
   |----------|--------|--------------|
   | 01       | Weiß   | 1            |
   | 0100011  | Schwarz| 3            |
   | 1001001  | Weiß   | 1            |
   | 0010010  | Schwarz| 2            |
   | 1001011  | Weiß   | 1            |
   | 0011011  | Schwarz| 2            |
   | 0010100  | Weiß   | 1            |
   | 1001011  | Schwarz| 1            |

2. Zeichnen der Grafik (W = Weiß, S = Schwarz):

W S S S S S S W
S W W W W W W S
W S S W W W W W
S W W W S W W W
W S S W W W W S
S W W W W W W W
W S S W S W W S
S W W W W W W W


### Aufgabe 5: LZW-Verfahren

a. **LZW-Codierung für das Wort „ANANAS“:**
- Initiales Dictionary: {A: 1, N: 2, S: 3}
- Ergebnis: 1, 2, 256, 257
- Dekodierung: ANANAS

b. **LZW-Code „ERDBE<256>KL<260>“ dekomprimieren:**
- Initiales Dictionary: {E: 1, R: 2, D: 3, B: 4, K: 5, L: 6}
- Ergebnis: ERDBERBKLBEKRL

### Aufgabe 6: BWT-Verfahren

a. **BWT für das Wort „ANANAS“:**
- Rotationstabelle erstellen:

ANANAS$
NANAS$A
ANAS$AN
NAS$ANA
AS$ANAN
S$ANANA
$ANANAS

- Sortierte Tabelle:

$ANANAS
ANANAS$
ANAS$AN
AS$ANAN
NANAS$A
NAS$ANA
S$ANANA

- BWT-Ergebnis: SSANAAN

b. **Code „IICRTGH6“ in der Burrows-Wheeler-Transformation dekodieren:**
- Resultat: „THRIFT“

### Aufgabe 7: ZIP-Komprimierung

a. **ASCII-Textdateien erstellen und zippen:**
- Zufällige Zeichen generieren und speichern.
- Dateien zippen und Größen analysieren.

b. **Speichergrößen in EXCEL-Tabelle auswerten:**
- Datei 1: 10 Zeichen
- Datei 2: 100 Zeichen
- Datei 3: 1000 Zeichen
- Datei 4: 10,000 Zeichen
- Datei 5: 100,000 Zeichen

c. **Ergebnisse interpretieren:**
- Je länger die Datei, desto effizienter die Komprimierung.

d. **ASCII-Datei mit 100,000 „A“ Zeichen zippen:**
- Resultat: deutlich kleinere ZIP-Datei.

e. **JPG-Bilder zippen und vergleichen:**
- Schon komprimierte Bilder bieten weniger Reduktionspotenzial.

### Aufgabe 8: Verlustlose Komprimierung

- **Verfahren:** Huffman, LZW, BWT, ZIP, PNG, FLAC.
- **Daten:** Textdateien, Programmcode, Bilder (PNG), Audio (FLAC).
- **Verlustbehaftete Komprimierung:** Ein Brief oder Java-Sourcecode würde durch Verlustbehaftung unbrauchbar, da die exakte Information nicht erhalten bleibt.

## Tag 1 Aufgaben

### Umwandlungstabellen und Binärrechnung

#### Aufgabe 1: Umwandlungstabellen

| DEC | HEX | BIN  | BIN 20^3 | BIN 20^2 | BIN 20^1 | BIN 20^0 |
|-----|-----|------|----------|----------|----------|----------|
| 0   | 0   | 0000 | 0        | 0        | 0        | 0        |
| 1   | 1   | 0001 | 0        | 0        | 0        | 1        |
| 2   | 2   | 0010 | 0        | 0        | 1        | 0        |
| 3   | 3   | 0011 | 0        | 0        | 1        | 1        |
| 4   | 4   | 0100 | 0        | 1        | 0        | 0        |
| 5   | 5   | 0101 | 0        | 1        | 0        | 1        |
| 6   | 6   | 0110 | 0        | 1        | 1        | 0        |
| 7   | 7   | 0111 | 0        | 1        | 1        | 1        |
| 8   | 8   | 1000 | 1        | 0        | 0        | 0        |
| 9   | 9   | 1001 | 1        | 0        | 0        | 1        |
| 10  | A   | 1010 | 1        | 0        | 1        | 0        |
| 11  | B   | 1011 | 1        | 0        | 1        | 1        |
| 12  | C   | 1100 | 1        | 1        | 0        | 0        |
| 13  | D   | 1101 | 1        | 1        | 0        | 1        |
| 14  | E   | 1110 | 1        | 1        | 1        | 0        |
| 15  | F   | 1111 | 1        | 1        | 1        | 1        |

#### Aufgabe 2: Umwandlung von Dezimal in Binär

Umwandlung von Dezimalzahl 911 in Binär:
- Die Binärzahl für 911 ist `1110001111`.

#### Aufgabe 3: Umwandlung von Binär in Dezimal

Umwandlung von Binärzahl `1011'0110` in Dezimal:
- Die Dezimalzahl für `1011'0110` ist 182.

#### Aufgabe 4: Umwandlung von Binär in Hexadezimal

Umwandlung von Binärzahl `1110'0010'1010'0101` in Hexadezimal:
- Die Hexadezimalzahl für `1110'0010'1010'0101` ist `E2A5`.

#### Aufgabe 5: Addition von binären Zahlen

Addition der binären Zahlen `1101'1001` und `0111'0101`:
- Das Ergebnis der Addition von `1101'1001` und `0111'0101`, unter Berücksichtigung von nur 8 Binärstellen, ist `1000'1110`.
