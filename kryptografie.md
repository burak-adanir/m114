# Inhaltsverzeichnis

## Symmetrische Verschlüsselungsverfahren
1. [Rotationschiffre](#rotationschiffre)
2. [Vigenèreverschlüsselung](#vigenèreverschlüsselung)
3. [Vigenèrecodeanalyse](#vigenèrecodeanalyse)
4. [XOR-Stromchiffre](#xor-stromchiffre)

## Asymmetrische Verschlüsselungsverfahren
1. [Diffie-Hellman](#diffie-hellman)
2. [RSA-Verschlüsselung](#rsa-verschlüsselung)

## Hybride Verschlüsselungsverfahren
1. [Hashwert](#hashwert)
2. [Schlüsselverwaltung](#schlüsselverwaltung)
3. [Public-Key-Verifizierung](#public-key-verifizierung)
4. [Public Key Infrastruktur (PKI)](#public-key-infrastruktur-pki)
5. [Certification-Authority (CA) und Trust-Center (TC)](#certification-authority-ca-und-trust-center-tc)

# Symmetrische Verschlüsselungsverfahren

## Rotationschiffre
Benutzen Sie CrypTool1 und finden Sie heraus, um welche Zitate es sich handelt! Die Rotationschiffre ist übrigens ein klassisches, symmetrisches Verfahren. Machen Sie eine Kryptoanalyse mit einem ASCII-Histogramm. (Tipp: Häufigkeitsanalyse der im Text enthaltenen Buchstaben)

**Lösung:**

«DER ANGRIFF ERFOLGT ZUR TEEZEIT DIE WUERFEL SIND GEFALLEN ICH KAM SAH UND SIEGTE TEILE UND HERRSCHE»

Das ASCII-Histogramm ergibt als häufigstes Zeichen im chiffrierten Text das «H». Da in deutschen (wie auch englischen) Schriften das «E» am Häufigsten vorkommt, wurde der Text mit dem Schlüssel 3 (ROT-3) verschlüsselt.

## Vigenèreverschlüsselung
Um etwas warm zu laufen, verschlüsseln wir, diesmal ohne Cryptool, das Wort BEEF mit dem Schlüsselwort AFFE.

BJJJ

ENIGMA

## Vigenèrecodeanalyse
Nun wird es spannender: Wir versuchen den Vigenère-Code zu knacken und bedienen uns einem Analysewerkzeug im Cryptool1. Abgefangen haben wir die folgende Vigenère-Chiffre:


Neugierig wie wir sind, möchten wir gerne wissen, welcher Text hinter dieser Chiffre steckt. Da uns aber das Schlüsselwort fehlt, müssen wir tief in unsere Trickkiste greifen.

**Lösung:**

Der Originaltext lautet:

«DER STAAT BIN ICH ES IST AEUSSERST SCHWIERIG ZU REDEN OHNE VIEL ZU SAGEN ICH MACHE MIT JEDER ERNENNUNG NEUNUNDNEUNZIG UNZUFRIEDENE UND EINEN UNDANKBAREN LOUIS XIV»


## XOR-Stromchiffre
Verschlüsseln Sie die Dezimalzahl 4711 von Hand als XOR-Stromchiffre. Der binäre Schlüssel lautet: 1000'1101. Zur Kontrolle entschlüsseln Sie die erhaltene Chiffre wieder.

**Lösung:**

„4711“ ergibt binär „0001'0010'0110'0111“
„0001'0010'0110'0117“ (Klartext)
„1000‘1101'1000‘1101“ (2x wiederholter Key XOR verknüpft)
„1001'1111'1110'1010“ (ergibt diese Chiffre)

# Asymmetrische Verschlüsselungsverfahren

## Diffie-Hellman
Spielen Sie in Cryptool1 einen Schlüsseltausch gemäss Diffie-Hellman durch. Experimentieren Sie mit verschiedenen, auch eigenen Parametern. (Sie finden das Tool unter Einzelverfahren→Protokolle→Diffie-Hellman-Demo...)

## RSA-Verschlüsselung
Erzeugen Sie zwei asymmetrische Schlüsselpaare: Eines für „Muster Felix“ und eines für „Hasler Harry“ (Sie finden das Tool unter Digitale Signaturen/PKI→PKI→Schlüssel erzeugen/importieren...) Verschlüsseln Sie nun eine Nachricht für Muster Felix und versuchen Sie danach, den Text als Hasler Harry, danach als Muster Felix zu entschlüsseln. Was stellen Sie fest? (Sie finden die Tools unter Ver-/Entschlüsseln→Asymmetrisch→RSA-Ver/Entschlüsselung...)

# Hybride Verschlüsselungsverfahren

Moderne Verschlüsselungsverfahren arbeiten hybrid. Schauen Sie sich dazu die beiden Demos zu RSA-AES an. (Sie finden die Tools unter Ver-/Entschlüsseln→Hybrid→RSA-AES-Ver/Entschlüsselung...)

## Hashwert
Führen Sie nun im Cryptool die Hash-Demo aus. Sie finden diese unter Einzelverfahren → Hashverfahren → Hash-Demo...

# Schlüsselverwaltung

## Public-Key-Verifizierung
Wie kann ich einen Public-Key verifizieren?

**Lösung:** Bei einer Zertifizierungsstelle.

# Public Key Infrastruktur (PKI)

Was versteht man unter Public Key Infrastruktur (PKI)?

**Lösung:** System, das digitale Zertifikate ausstellen, verteilen und prüfen kann.

# Certification-Authority (CA) und Trust-Center (TC)

Was bedeutet Certification-Authority (CA) und was Trust-Center (TC)?

**Lösung:** Als Trust Center (TC) oder vertrauenswürdig wird eine Instanz bezeichnet, die technisch, organisatorisch und betrieblich so ausgestattet ist, dass sie ihre Aufgaben in vertrauenswürdiger Weise durchführt - unabhängig von den Endanwendern. Dieser Instanz wird von anderen Instanzen (u.a. von Endanwendern, Kommunikationspartnern) hinsichtlich der erbrachten Sicherheitsfunktionen vertraut. Die Instanzen werden auch als "Trusted Third Parties (TTP)" bezeichnet. Vertrauenswürdige Instanzen können folgenden Funktionen wahrnehmen:

Zertifizierungsstellen (Certification Authorities)
Schlüsselmanagement-Center (Key-Management-Center)
Schlüssel-Archive (Key-Recovery(Escrow)-Center)

