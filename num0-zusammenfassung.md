
# Num 0 WS 22/23 Widerholung/Zusammenfassung 

**Disclaimer**: Nicht volstaendig, viele Schreib-/Deutschfehler

## Format

*  **Frage 1**: Kleine Verstaendnissfragen 10 $\times$ 2p = 20p 
*  **4 laengere Fragen**: $\times$ 10p = 40p (*besten 3 zaehlen)* 

## Stoff

*  Gesammte Skript ausser Kapitel: 
	*  4.4
	*  5.2.2
	*  5.3
	*  5.4.3
	*  6.3  *Kommt in der 2ten Klausur*:
	*  6.4  *Kommt in der 2ten Klausur*:
*  Alle Uebungsblaetter
* Keine Programmieraufgaben aber algorithmische Fragen schon 
*  Alle Definitionen & alle Saetze (*nicht nur die Aussage aber auch die Voraussetzungen*)
*  **Nicht erwartet**: Komplizierte Formel auswendig kennen. (*wenn Gegenstad einer Frage dann angegeben + herleiten oder als Hinweis gegeben*)
*  **Hintergrundwissen**: LA & Analysis

## Zusammenfassung

### 2 - Konditionierung & Stabilitaet

* Definition einer numerischen Aufgabe - absolute/relativer Fehler
*  Relative Konditionszahl (Fehlerdaempfung, -verstaerkung)
*Only general understanding of these concepts is expected*

#### 2.3 & 2.4 Zahlendarstellung & Rundungsfehler

* Maschinenzahlen/ -operationen
* Fliesskommagitter, IEEE double precision
* Groesste, kleinste darstellbare Zahl (positive/negative)
* (natuerliche) Rundung - absolute/relative Rundungsfehler
* Maschinengenauigkeit  `eps` $\rightarrow$ Vorwaertsfehleranalyse
	$$ x\oplus y = (x + y)(1 + eps) \,  \quad |\epsilon | < eps $$
*solche Rechnungen koennen an der Klausur drankommen*

### 3 - Interpolation & Bestapproximation

* Was ist Interpolation/ Best Approximation?
* 2 Wichtige Saetze:
	* Fehler Darstellung (**Satz 3.5**)
	* Existenz und Eindeutigkeit der Loesung (**Satz 3.8**)
* Lagrange Darstellung
* Newton Darstellung (**Herleitung mittels dividierenden Differenzen - Satz 3.10**)
* Neville & Horner Schema fuer Polynomauswertung
* Allgemeine Interpolationsfehler (**Satz 3.12**)
	* Abschaetzung in $||\cdot ||_{\infty}$      
* Richardson Extrapolation zum Limes (**Satz 3.16**)
	* Anwendung bei numerischen Differentiation
* Stueckweise Polynominterpolation (*z.B. Stueckweise Linear*)
* Kubische Splineinterpolation
	* Def  & Existenz (**Satz 3.21**)
	* Minimale Kruemmung
* Approximationsfehler (**Satz 3.23 ohne Beweis**)
* Trigonometrische Interpolation (*Beweis nicht so wichtig fuer die Klausur*)
	* 2 wichtige Punkte:
		* Gibbs Phaenomen
		* FFT (*keine Details, nur Ideen*)
* Best Approximation
	* $\mathcal{L}^2-\text{Skalarprodukt}$ & $\mathcal{L}^2 - \text{Norm}$ $\rightsquigarrow$ Gaussapproximation
	* Orthogonalitaet des Bestapproximationsfehlers $\rightsquigarrow$ Gauss-Legendre Polynome (*Formel muessen nicht auswendig gelernt werden*) 
	* Allgemeine Gaussaproximation (**Satz 3.31**)
		* Garantierter Fehlerkontrolle
		* Haar-Wavelettes Definitionen: 
			* Mother Wavelette
			* Erhalten von Kinder Wavelettes durch Skalierungen/Verschiebungen
		* Eigenschaften (**Lemma 3.34 - wichtigste Teil dises Unterkapitels**)
		* Transformationssatz (*ohne Beweis*)
		* Greedy Algorithmus um adaptiv eine Basis zu finden

### 4 - Quadratur (Numerische Integration)

* Quadraturformeln
* Fehlerdarstellung (**Satz 4.2**)
* **Sehr wichtig**: Genaugkeitsgrad
* **Newton-Cotes Formeln** (aequidistante Punkte) (**Trapez, Simpsonsregeln auswendig kennen sehr wichtig**)
	* Fehler Darstellung fuer Newton-Cotes (**Lemma 4.11 & Satz 4.12**)
* Summierte Newton-Cotes Fehler (**Korollar 4.12**)
* Adaptive Summierte Simpsonsregel (*Nur algorithmische Idee*)
* **Gausquadratur** (nicht Aequidistante Stuetzstellen) $\rightsquigarrow$ Maximale Genauigkeitsgrad (**Lemma 4.21 & Bedingungen im Lemma 4.22**)
	* Beispiele mit 1 Punkt & 2 Punkte (*wichtig die Bedingungen zu kennen - Legendre Polynome*)
	* Allgemeine Gaussquadraturformel $\rightsquigarrow$ Nullstellen der Legendrepolynome (**Satz 4.26**)
	* Konvergenzsatz (nur Idee) (**Satz 4.30 - nicht notwendig fuer die Klausur**)

### 5 - Lineare Gleichungssysteme - Direkte Verfahren

* Loesung von $Ax = b$ mit  $A \in \mathbb{R}^{m\times n},  \, m < n, \, m = n, \, m > n$  
* Loesbarkeit fuer $m = n$ 
* **Matrixnormen (sehr wichtig)**
	* Normaequivalenz in $\mathbb{R}^{m}$ (**Satz 5.5**)
	* Eigenschaften von Matrixnormen (**sehr wichtig**):
		* Vertraeglich
		* Submultiplikativ
		* natuerliche Matrixnorm
	* Zeilen- & Spaltensumennormen (**wichtigsten Matrix normen - Lemma 5.8**)
	* Eigenwerten/-vektoren
		* $\forall\lambda , \, || \cdot || \text{ natuerlich:} \quad |\lambda | \leq || A ||$  *d.h. Spektrum sind durch Matrixnormen beschraenkt*
	* Symmetrische, transponierte, orthogonale, positiv-definite Matrix
	*  Eigenschaften von symmetrischen Matrizen im Bezug auf Spektrum
		*  Spektralnorm $|| \cdot ||_{2}$ ist die natuerliche Norm zu Euklidischem Vektornorm
	* Fehleranalyse: Konditionszahl (**Def 5.15**)
		* Stoerungssatz (**Satz 5.17, Lemma 5.16**)
	*  Gausseliminationsverfahren: Verfahren, Matrixschreibweise
		* LR Zerlegung
		* Pivotierung
		* Vorwaerts/-Rueckwertseinsetzung
		* Komplexitaet des Gaussverfahrens und der LR Zerlegung (**Lemma 5.24**)
		* Rueckwertsstabilitaet der LR-Zerlegung mit Spaltenpivotierung (**Nur Idee von Lemma 5.30, Satz 5.31 & 5.35 ohne Beweis**)
		* Anwendung des Stoerungsatzes
		* Aequilibrierung (**Rest von LR & Cholesky nicht in der Klausur**)
		* Falls $m \neq n$: Least-square3s Loesung $\iff$ Loesung der Normalgleichung, $!\exists$ (**Satz 5.40 !!!**)
		* QR-Zerlegung: 
			* Householder Transformation (**Def 5.4**)
			* Eigenschaften Householderverfahren (**Lemma 5.42 - nur Ideen**)
			* Eigenschaften der QR-Zerlegung $\rightsquigarrow$ Loesungsverfahren fuer $\text{rang}(A) = \text{min}(m, n)$ (!!!)
			* Anwendung in der Gausschen Ausgleichsrechnung (!!!)

### 6 - Iterative Verfahren

* $F(x) = 0,  \quad F:\mathbb{R}^n\rightarrow\mathbb{R}^n$, 
* Iterationsfunktion, Fixpunktiteration
* Leipschitzstetigkeit, Kontraktion (beides bzgl einer Teilmenge $U \subset \mathbb{R}^n$, *Definition 6.1*)
* Banachsche Fixpunktsatz (**Sat 6.2**)
* Wie definieren wir Konvergenzordnung/-faktor (**Definition 6.3**)
* Newtonverfahren (**auswendig kennen fuer die Klausur !**)
	* Herleitung ueber Taylor, geometrische Interpretation
* Jacobi-matrix 
	* Invertierbarkeit der Jacobimatrix (**Lemma 6.7*) $\rightsquigarrow$ quadratische Konvergenz (*Satz 6.9 - ohne Beweis via Lemma 6.8**)
* *Kommt nur in der Wiederholungsklausur*:
	* 6.3: Jacobi, GS...
	* 6.4: Numerische Loesung von Diffgleichungen 
