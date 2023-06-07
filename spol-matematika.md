# Společná matematika

## 1. Základy diferenciálního a integrálního počtu

### Posloupnosti reálných čísel a jejich limity

#### Definice, aritmetika limit

Nechť $M$ je množina. Posloupnost s hodnotami v $M$ je zobrazení z $\mathbb{N}$ do $M$. Každé přirozené číslo $n$ je tedy zobrazeno na nějaký prvek $a_n$ množiny $M$, tomu říkáme $n$-tý prvek posloupnosti. Posloupnost $(a_1, a_2, a_3, ...)$ značíme $(a_n)$ nebo $(a_n)^\infty_{n=1}$. $(a_n) \subset M$ značí posloupnost s hodnotami v $M$.

Posloupnost může být:
- shora omezená pokud $\exists K \in \mathbb{R}$ takové, že $\forall n \in \mathbb{N}: a_n < K$,
- zdola omezená pokud $\exists K \in \mathbb{R}$ takové, že $\forall n \in \mathbb{N}: a_n > K$,
- omezená pokud je shora i zdola omezená,
- rostoucí pokud $a_n < a_m$ pro každé $n < m$,
- neklesající pokud $a_n \leq a_m$ pro každé $n < m$,
- klesající pokud $a_n > a_m$ pro každé $n < m$,
- nerostoucí pokud $a_n \geq a_m$ pro každé $n < m$,
- monotónní pokud je neklesající nebo nerostoucí.

Vlastní limita: Nechť $(a_n)$ je posloupnost reálných čísel. $A \in \mathbb{R}$ je vlastní limita takové posloupnosti, pokud pro každé reálné $\epsilon > 0$ existuje $n_0 \in \mathbb{N}$ takové, že pro každé $n \geq n_0$ je $|a_n - A| < \epsilon$. Pokud posloupnost má vlastní limitu, pak konverguje a píšeme $\lim_{n \rightarrow \infty} a_n = A$.

Nevlastní limita: Nechť $(a_n)$ je posloupnost reálných čísel. Posloupnost má nevlastní limitu $\infty, \lim_{n \rightarrow \infty} a_n = \infty$, pokud pro každé reálné číslo $K$ existuje $n_0$ takové, že pro každé $n \geq n_0$ platí $a_n > K$. Obdobně pro $-\infty$, stačí otočit poslední nerovnost.

Každá posloupnost reálných čísel má nejvýše jednu limitu (vlastní či nevlastní).

Je-li posloupnost reálných čísel neklesající a shora omezená, pak konverguje.

Posloupnost $(b_n)$ je podposloupností posloupnosti $(a_n)$, pokud existuje $f: \mathbb{N} \rightarrow \mathbb{N}, b_n = a_{f(n)}$. Je zřejmé, že relace "být podposloupností" je tranzitivní a reflexivní, ale ne antisymetrická.

Je-li $(b_n)$ podposloupnost $(a_n)$ a $\lim_{n \rightarrow \infty} a_n = a \in \mathbb{R}^*$, pak i $\lim_{n \rightarrow \infty} b_n = a$.

Aritmetika limit: Nechť $(a_n), (b_n)$ jsou posloupnosti reálných čísel s $\lim_{n \rightarrow \infty} a_n = a \in \mathbb{R}^*, \lim_{n \rightarrow \infty} b_n = b \in \mathbb{R}^*$. Pak platí:
1. $\lim_{n \rightarrow \infty} (a_n + b_n) = a + b$
2. $\lim_{n \rightarrow \infty} (a_n b_n) = ab$
3. pokud $b_n \not = 0$ pro každé $n > n_0$, pak $\lim_{n \rightarrow \infty} (a_n / b_n) = a/b$

Všechny uvedené věty platí, pokud výraz na pravé straně je definován.

#### Věta o dvou policajtech, limity a uspořádání

Nejprve o uspořádání: Nechť posloupnosti $(a_n), (b_n) \subset \mathbb{R}$ mají vlastní limity $\lim_{n \rightarrow \infty} a_n = a, \lim_{n \rightarrow \infty} b_n = b$.
1. Když $a < b$, tak existuje $n_0$, že $n > n_0 \implies a_n < b_n$.
2. Když $a_n \leq b_n$ pro každé $n > n_0$, pak $a \leq b$.

Toto platí i pro nevlastní limity, ovšem je třeba dát si pozor na rovnost.

O dvou policajtech: Nechť posloupnosti $(a_n), (b_n), (c_n) \subset \mathbb{R}$ splňují $\lim_{n \rightarrow \infty} a_n = \lim_{n \rightarrow \infty} b_n = a \in \mathbb{R}$ a pro každé $n > n_0$ platí $a_n \leq c_n \leq b_n$. Pak $(c_n)$ konverguje a $\lim_{n \rightarrow \infty} c_n = a$.

### Řady

Nekonečná řada je výraz $\sum^\infty_{n=1}a_n = a_1 + a_2 + ...$, kde $(a_n)$ je posloupnost reálných čísel.

#### Definice částečného součtu a součtu

Částečný součet řady $s_n$ je součet prvních $n$ členů. Pokud existuje vlastní limita posloupnosti $(s_n)$ částečných součtů řady, pak mluvíme o konvergentní řadě a $\lim_{n \rightarrow \infty} (s_n)$ je jejím součtem. Pokud limita neexistuje nebo je nevlastní, jde o divergentní řadu.

#### Geometrická řada, harmonická řada

Geometrická řada: $\sum_{n=0}^\infty q^n = 1 + q + q^2 + ...$, kde $q \in \mathbb{R}$ značíme kvocient. Pro součet geom. řady platí, že
1. pro $-1 < q < 1$ je součet $\frac{1}{1-q}$
2. pro $q \geq 1$ je součet $+\infty$
3. pro $q \leq -1$ součet neexistuje.

Dalším příkladem jsou řady typu $\sum_{n=1}^\infty \frac{1}{n^s} = 1 + \frac{1}{2^s} + ...$, pro $s = 1$ mluvíme o harmonické řadě. Ačkoliv prvky řady jdou k nule, tak řada diverguje.

### Reálné funkce jedné reálné proměnné

Funkce $f: M \rightarrow \mathbb{R}, M \subseteq \mathbb{R}$ je

- shora omezená pokud $\exists K \in \mathbb{R}$ takové, že $f(x) < K$ pro každé $x \in M$,
- zdola omezená pokud $\exists K \in \mathbb{R}$ takové, že $f(x) < K$ pro každé $x \in M$,
- omezená pokud je shora i zdola omezená,
- rostoucí pokud $f(x) < f(y)$ pro každé $x, y \in M, x < y$,
- neklesající pokud $f(x) \leq f(y)$ pro každé $x, y \in M, x < y$,
- klesající pokud $f(x) > f(y)$ pro každé $x, y \in M, x < y$,
- nerostoucí pokud $f(x) \geq f(y)$ pro každé $x, y \in M, x < y$,
- monotónní pokud je neklesající nebo nerostoucí,
- periodická funkce s periodou $p \in \mathbb{R}, p > 0$, když pro každé $x \in M$ je i $x \pm p \in M, f(x) = f(x \pm p)$,
- prostá pokud $x \not = y \implies f(x) \not = f(y)$.

Nechť $f: M \rightarrow \mathbb{R}$ je prostá funkce. $f^{-1}$ je inverzní funkce k $f$, pokud $f^{-1}(y) = x \iff f(x) = y$.

Funkce mohou být definovány řadou - třeba exponenciála, sinus, cosinus.

Okolí bodu $a \in \mathbb{R}$, respektive $\delta$-okolí pro $\delta > 0, \delta \in \mathbb{R}$ je inverval $U(a, \delta) = (a - \delta, a + \delta)$. Jinak zapsáno $U(a, \delta) = \{ x \in \mathbb{R}: |x - a| < \delta \}$. Okolí nekonečen definujeme $U(+\infty, \delta) = (1/\delta, +\infty), U(-\infty, \delta) = (-\infty, -1/\delta)$. Pravé okolí defingujeme jako $U^+(a, \delta) = [a, a + \delta)$, levé okolí obdobně. Prstencová okolí bodu jsou stejná, akorát neobsahují bod $a$.

#### Limita funkce v bodě

##### Definice, aritmetika limit

Řekněme, že funkce $f$ má v bodě $a \in \mathbb{R}^*$ limitu $A \in \mathbb{R}^*$, když $\forall \epsilon > 0 \exists \delta > 0: x \in P(a, \delta) \implies f(x) \in U(A, \epsilon)$. Zapisujeme $\lim_{x \rightarrow a} f(x) = A$. Jednostranné limity definujeme obdobně, pro limitu zprava značíme $\lim_{x \rightarrow a^+} f(x) = A$ a místo prstencového okolí z definice uvažujeme prstencové pravé okolí, opět obdobně pro limitu zleva.

Jestliže se rovnají limita pro jeden bod zleva i zprava, pak se takovému číslu rovná i limita v daném bodě. Naopak, pokud se limity liší, pak limita neexistuje. Funkce má v daném bodě nejvýše jednu limitu.

Heineho definice limity funkce: Nechť $f$ je definovaná na prstencovém okolí $P(a, \delta)$ bodu $a$ pro $\delta > 0$. Pak jsou následující tvrzení ekvivalentní:
1. $\lim_{x \rightarrow a} f(x) = A$,
2. pro každou posloupnost $(x_n) \subset P(a, \delta)$ takovou, že $x_n \not = a$ pro každé $n \in \mathbb{N}, \lim_{n \rightarrow \infty} x_n = a$ platí, že $\lim_{n \rightarrow \infty} f(x_n) = A$.

Aritmetika limit: Nechť $a, A, B \in \mathbb{R}^*$ a $f, g$ funkce definované na prstencovém okolí $P(a, \delta)$ bodu $a$ a platí $\lim_{x \rightarrow a} f(x) = A, \lim_{x \rightarrow a} g(x) = B$. Pak platí:
1. $\lim_{x \rightarrow a} f(x) + g(x) = A + B$,
2. $\lim_{x \rightarrow a} f(x) g(x) = AB$,
3. pro $g(x)$ nenulovou na prstencovém okolí $a$ platí $\lim_{x \rightarrow a} f(x)/g(x) = A/B$.

Uvedené věty platí ve chvíli, kdy jsou pravé strany definované.

##### Vztah s uspořádáním

Nechť $c \in \mathbb{R}^*$ a funkce $f, g, h$ jsou definované na prstencovém okolí bodu $c$. Pak:
1. Mají-li $f, g$ v bodě $c$ limitu a $\lim_{x \rightarrow c} f(x) > \lim_{x \rightarrow c} g(x)$, pak existuje $\delta > 0$ takové, že $f(x) > g(x)$ pro každé $x \in P(c, \delta)$.
2. Existuje-li $\delta > 0$ takové, že $f(x) \geq g(x)$ pro každé $x \in P(c, \delta)$ a mají-li funkce $f, g$ limitu v bodě $c$, potom $\lim_{x \rightarrow c} f(x) \geq \lim_{x \rightarrow c} g(x)$.
3. Existuje-li $\delta > 0$ takové, že $f(x) \leq h(x) \leq g(x)$ pro každé $x \in P(c, \delta)$ a $\lim_{x \rightarrow c} f(x) = \lim_{x \rightarrow c} g(x) = A \in \mathbb{R}^*$, potom i $\lim{x \rightarrow c} h(x) = A$.

##### Limita složené funkce

Nechť $A, B, C \in \mathbb{R}^*$, nechť $g(x)$ je funkce splňující $\lim_{x \rightarrow A} g(x) = B$ a $f(x)$ je funkce splňující $\lim_{x \rightarrow B} f(x) = C$ a je splněna jedna z podmínek:
1. $f(x)$ je spojitá v $B$, tedy $f(B) = \lim_{x \rightarrow B} f(x) = C$
2. Na nějakem prstencovém okolí $P(A, \mu)$ funkce $g(x)$ nenabývá hodnotu $B$, tedy $B \not \in g(P(A, \mu))$.

Potom $\lim_{x \rightarrow A} f(g(x)) = C$.

#### Funkce spojité na intervalu

Funkce $f$ je spojitá v bodě $b \in \mathbb{R}$, pokud platí $\lim_{x \rightarrow b} f(x) = f(b)$.

Nechť $I \subseteq \mathbb{R}$ je interval a $f: I \rightarrow \mathbb{R}$ je funkce na něm definovaná. Pak je $f$ na intervalu $I$ spojitá, je-li spojitá v každém vnitřním bodu $I$ a na krajích $I$ je odpovídajícím způsobem jednostranně spojitá.

##### Věta o nabývání mezihodnot (Darbouxova)

Nechť $a < b$ jsou reálná čísla a funkce $f: [a, b] \rightarrow \mathbb{R}$ je na intervalu $[a, b]$ spojitá. Označme $m = min\{f(a), f(b)\}, M = max\{f(a), f(b)\}$. Pak každé reálné číslo z intervalu $[m, M]$ je hodnotou funkce $f$, tedy $\forall y \in [m, M] \exists \alpha \in [a, b]: f(\alpha) = y$.

##### Věta o nabývání maxima

Nejprve si maximum funkce a další extrémy definujme.

Nechť $M \subseteq \mathbb{R}, f: M \rightarrow \mathbb{R}$. Řekněme, že funkce $f$ v bodě $a \in M$ nabývá svého:
- minima, když $\forall x \in M: f(x) \geq f(a)$
- maxima, když $\forall x \in M: f(x) \geq f(a)$
- ostrého minima, když $\forall x \in M, x \not = a: f(x) > f(a)$
- ostrého maxima, když $\forall x \in M, x \not = a: f(x) < f(a)$
- lokálního minima, když $\exists \delta > 0 \forall x \in M \cap U(a, \delta): f(x) \geq f(a)$
- lokálního maxima, když $\exists \delta > 0 \forall x \in M \cap U(a, \delta): f(x) \leq f(a)$

Teď se můžeme přesunout k principu maxima pro spojité funkce. Nechť $a, b \in \mathbb{R}, a \leq b$ a $f: [a, b] \rightarrow \mathbb{R}$ je spojitá funkce. Potom $f$ nabývá na intervalu $[a, b]$ svého maxima i minima.

### Derivace a její aplikace

#### Definice a základní pravidla pro výpočet

Nechť $f: M \rightarrow \mathbb{R}, b \in M, U(b, \delta) \subseteq M$ pro nějaké $\delta > 0$. Derivace funkce $f$ v bodě $b$ je limita $f'(b) = \lim_{h \rightarrow 0} \frac{f(h + b) - f(b)}{h} = \lim_{x \rightarrow b} \frac{f(x) - f(b)}{x - b}$. Podobně definujeme i jednostranné derivace. Derivace existují podobně jako limity v případě, že se jednostranné derivace rovnají. Jestliže má funkce v nějakém bodě vlastní derivaci, pak je v bodě diferenciovatelná a navíc i spojitá (důsledek).

Derivace vyšších řádů definujeme následovně: $f^{(n)}(a) = \lim_{x \rightarrow a} \frac{f^{(n-1)}(x) - f^{n-1}(a)}{x-a}$.

Aritmetika derivací: Nechť $f, g: U(b, \delta) \rightarrow \mathbb{R}$ jsou funkce mající v $b$ derivaci. Pak platí (jsou-li pro výraz pravé strany definované):
1. $(f + g)'(b) = f'(b) + g'(b)$
2. Pro $\alpha \in \mathbb{R}: (\alpha f)'(b) = \alpha(f(b))$
3. Leibnizova formule: $(fg)'(b) = f'(b)g(b) + f(b)g'(b)$
4. Je-li $g$ spojitá v $b, g(b) \not = 0$, pak $(\frac{f}{g})'(b) = \frac{f'(b)g(b) - f(b)g'(b)}{g(b)^2}$

Derivace inverzní funkce: $(f^{-1})'(b) = \frac{1}{f'(b)}$, pokud je $f'(b) \not = 0$, pro nulovou derivaci jde o nevlastní derivaci.

#### L’Hospitalovo pravidlo

Nechť $a \in \mathbb{R}^*$, nechť funkce $f, g: P(a, \delta) \rightarrow \mathbb{R}$ mají na prstencovém okolí $a$ vlastní derivaci a $g'(x) \not = 0$ na $P(a, \delta)$.
1. Pokud $\lim_{x \rightarrow a} f(x) = \lim_{x \rightarrow a} g(x) = 0$ a $\lim_{x \rightarrow a} f'(x)/\lim_{x \rightarrow a} g'(x) = A \in \mathbb{R}^*$, pak $\lim_{x \rightarrow a} f(x)/\lim_{x \rightarrow a} g(x) = A$.
2. Pokud $\lim_{x \rightarrow a} |g(x)| = +\infty, \lim_{x \rightarrow a} f'(x)/\lim_{x \rightarrow a} g'(x) = A$, pak $\lim_{x \rightarrow a} f(x)/\lim_{x \rightarrow a} g(x) = A$.

Totéž platí pro jednostranné limity.

#### Vyšetření průběhu funkcí: extrémy, monotonie a konvexita/konkavita

Pokud v bodě není nulová derivace, pak tam nemůže být lokální (a tedy ani globální) extrém. Pozor na to, že opačně to neplatí, pokud je v bodě derivace nula, tak sice může v bodě být extrém, ale určitě nemusí (protipříklad $x^3, x = 0$).

Monotonie derivace: Nechť je funkce $f$ spojitá na nedegenerovaném intervalu s kladnou délkou a má v každém vnitřním bodě derivaci. Pokud na vnitřku platí, že derivace je kladná, pak je funkce na intervalu rostoucí (pro neostrou rovnost neklesající). Obdobně, pokud je derivace funkce záporná, pak je funkce na intervalu klesající (respektive nerostoucí).

Konvexita/konkavita funkce: Nechť $I$ je otevřený interval, nechť funkce $f: I \rightarrow \mathbb{R}$ má na $I$ druhou derivaci. Pokud je druhá derivace funkce na intervalu kladná, pak je funkce na $I$ ryze konvexní (resp. konvexní pro neostrou nerovnost), pokud je druhá derivace $f$ záporná, pak je funkce na $I$ ryze konkávní (resp. konkávní pro neostrou nerovnost).

#### Taylorův polynom (limitní forma)

Taylorův polynom používáme pro aproximaci funkce nějakým polynomem stupně $n$. Pak tedy hledáme $\lim_{x \rightarrow a} \frac{f(x) - P(x)}{(x-a)^n} = 0$. 

Taylorův polynom splňuje právě $P(x)$ a je to jediný polynom splňující limitu nahoře. Nechť $a \in \mathbb{R}, n \in \mathbb{N}_0$ a $f$ je funkce definovaná na okolí $a$ a vlastní $n$-tou derivaci v bodě $a$. Taylorův polynom řádu $n$ funkce $f$ v bodě $a$ je polynom $T_n^{f,a}(x) = \sum_{i=0}^n \frac{f^{(i)}(a)}{i!}(x-a)^i = f(a) + f'(a)(x-a) + \frac{f''(a)}{2!}(x-a)^2 + ...$. Uvažujeme $0^0 = 1$.

Zbytek Taylorova polynomu definujeme obdobně následovně: Nechť $f$ je funkce, která má na otevřeném intervalu $I \subseteq \mathbb{R}$ vlastní derivaci řádu $n+1$. Volme $a, b \in I, a \not = b$. Pak $\exists a < c < b$ takový, že $R_n^{f,a}(b) = \frac{f^{(n+1)}(c)}{(n+1)!}(b-a)^{n+1}$.

Taylorova řada odpovídá Taylorově polynomu pro $n \rightarrow \infty$.

### Integrály a jejich aplikace

#### Primitivní funkce: definice a metody výpočtu (substituce, per-partes)

Nechť $-\infty \leq a < b \leq \infty, f: (a, b) \rightarrow \mathbb{R}$ je daná funkce. Pokud má funkce $F: (a, b) \rightarrow \mathbb{R}$ na $(a, b)$ derivaci a ta se rovná $f(x)$, tedy $F'(x) = f(x)$, pak je $F$ primitivní funkcí k $f$. Primitivní funkce je jednoznačná až na konstantu.

Je-li funkce na neprázdném otevřeném intervalu spojitá, pak má funkce na takovém intervalu primitivní funkci. Navíc má funkce s primitivní funkcí Darbouxovu vlastnost.

Pro některé primitivní funkce neexistuje vzorec, i přestože existují.

Věta o substituci: Buďte dány funkce $\varphi: (\alpha, \beta) \rightarrow (a, b), f: (a, b) \rightarrow \mathbb{R}$, přičemž první funkce má na prvním intervalu vlastní derivaci. Nechť je funkce $F: (a, b) \rightarrow \mathbb{R}$ na intervalu $(a, b)$ primitivní funkcí k $f$. Pak na $(\alpha, \beta)$ platí: $\int f(\varphi(t)) \cdot \varphi'(t) dt = F(\varphi(t)) + C$.

Věta o integraci per partes: Nechť jsou funkce $f, g$ spojité na intervalu $(a, b)$ a funkce $F, G$ jsou k nim funkce na daném intervalu primitivní. Potom i $fG, Fg$ mají na daném intervalu primitivní funkci a platí identita $\int f(x)G(x) dx + \int F(x)g(x) dx = F(x)G(x) + c$.

Tady si doporučuji projít nějaké řešené příklady.

#### Riemannův integrál: definice, souvislost s primitivní funkcí (Newtonovým integrálem)

Nejprve je dobré si zadefinovat si Newtonův integrál pro funkce. Máme dáno $a, b \in \mathbb{R}, a < b$. Funkce $f: (a, b) \rightarrow \mathbb{R}$ má Newtonův integrál, když má na intervalu primitivní funkci $F$ a ta má vlastní jednostranné limity $F(a^+) = \lim_{x \rightarrow a^+} F(x)$ a $F(a^-) = \lim_{x \rightarrow b^-} F(x)$. Symbolem $[F]^b_a$ poté označujeme rozdíl $F(b^-) - F(a^+)$. To také označujeme jako Newtonův integrál, tedy $(N) \int_a^b f(x) dx = [F]_a^b$.

Je-li funkce $f$ na $[a, b] \rightarrow \mathbb{R}$ spojitá, pak existuje příslušný Newtonův integrál. Pro určité integrály platí věta o substituci a metoda per partes stejně jako pro neurčitý integrál.

Teď si už můžeme zadefinovat Riemannův integrál. Nechť $-\infty < a < b < \infty$ jsou dvě reálná čísla. Konečná $(k+1)$-tice bodů $D = (a_0, a_1, ..., a_k)$ z intervalu $[a, b]$ je jeho dělením, pokud platí $a = a_0 < a_1 < ... < a_k = b$. Tyto body postupně dělí interval $[a, b]$ na intervaly $I_i = [a_i, a_{i+1}]$. Délku invertvalu označíme pomocí absolutní hodnoty. Pro nějakou funkci a její dělení (na intervalu $[a, b]$) definujeme dolní a horní Riemannovu sumu jako $s(f, D) = \sum_{i=0}^{k-1} |I_i| m_i$, respektive $S(f, D) = \sum_{i=0}^{k-1} |I_i| M_i$, kde $m_i = \inf\{f(x); x \in I_i\}, M_i = \sup\{f(x); x \in I_i\}$. Tyto součty jsou vždy definované a mohou být i $\pm \infty$.

Množinu všech newtonovsky integrovatelných funkcí na $[a, b]$ označujeme $\mathcal{N}[a, b]$, podobně pro riemannovsky integrovatelné funkce na $[a, b]$ to je $\mathcal{R}[a, b]$.

Poté je dolní Riemannův integrál definovaný jako $\underline{\int_{a}^{b}} f = \underline{\int_{a}^{b}} f(x) dx = \sup\{s(f, D): D $ je dělení $[a, b]\}$, obdobně $\overline{\int_{a}^{b}} f = \overline{\int_{a}^{b}} f(x) dx = \inf\{S(f, D): D $ je dělení $[a, b]\}$. Funkce je riemannovsky integrovatelná, popř. má Riemannův integrál, pokud $\underline{\int_{a}^{b}} f(x) dx = \overline{\int_{a}^{b}} f(x) dx \in \mathbb{R}$. Takový integrál pak také značíme $\int_{a}^{b} f(x) dx$.

Pro funkce, které nejsou omezené, neexistuje Riemannův integrál.

Pro interval $[a, b]$ a dvě různá dělení takového intervalu $D, D'$ platí, že $s(f, D) \leq s(f, D') \leq S(f, D') \leq S(f, D)$.

Kritérium integrovatelnosti: Nechť $f: [a, b] \rightarrow \mathbb{R}$. Potom $f \in \mathcal{R}[a, b] \iff \forall \epsilon > 0 \exists D: 0 \leq S(f, D) - s(f, D) < \epsilon$.

Je-li funkce $f: [a, b] \rightarrow \mathbb{R}$ na intervalu $[a, b]$ nerostoucí nebo neklesající, pak má Riemannův integrál. Obdobně platí, že je-li taková funkce na daném intervalu spojitá, pak také má Riemannův integrál.

Platí, že pokud existují oba integrály (tedy jak Riemannův, tak Newtonův), pak se hodnoty rovnají.

#### Aplikace

##### Odhady součtu řad (konečných i nekonečných)

Nechť $n \in \mathbb{N}$ a $f$ je neklesající funkce na $[1, n]$. Pak platí $\sum_{k=1}^{n-1} f(k) \leq \int_1^n f \leq \sum_{k=2}^n f(k)$.

Nechť $f: [1, \infty) \rightarrow [0, \infty)$ je nerostoucí nezáporná funkce. Potom řada $\sum^\infty_{k=1} f(k)$ konverguje právě tehdy, když $\lim_{b \rightarrow \infty} \int_1^b f < \infty$.

Pomocí těchto vět se dá například odhadnout součet harmonické řady, respektive její konvergenci.

##### Obsahy rovinných útvarů

Obsah rovinného útvaru pod grafem funkce, který je situován $a \leq x \leq b, 0 \leq y \leq f(x)$ je vlastně definován jako $\int_a^b f(x) dx$.

##### Objemy a povrchy rotačních útvarů v prostoru

Pro objem a povrch tělesa $V = \{(x, y, z) \in \mathbb{R}^3 | a \leq x \leq b \& \sqrt{y^2 + z^2} \leq f(x) \}$ vzniklého rotací kolem osy $x$ platí následující vzorce:
$objem(V) = \pi \int_a^b f(t)^2 dt$, $povrch(V) = 2\pi \int^b_a f(t) \sqrt{1+(f'(t))^2} dt$.

##### Délka křivky

Délka křivky $\{(x, f(x)) \in \mathbb{R}^2 | a \leq x \leq b\}$ je rovna $\int_a^b \sqrt{1+(f'(t))^2} dt$.

## 2. Algebra a lineární algebra

TODO

## 3. Diskrétní matematika

### Relace

Relace mezi množinami $X, Y$ je $R \subseteq X \times Y$. Může být:
- prázdná $\emptyset$
- univerzální $X \times Y$
- diagonální $\{(x, x) | x \in X\}$
- inverzní $\{ (y, x) | (x, y) \in R\}$
- složená $x(R \circ S)z \iff \exists y \in Y: xRy \land ySz$

#### Vlastnosti binárních relací (reflexivita, symetrie, antisymetrie, tranzitivita)

- reflexivita: $\forall x \in X: x R x$
- symetrie: $\forall x, y \in X: x R y \iff y R x$
- antisymetrie: $\forall x, y \in X, x \not = y: x R y \implies \lnot y R x$
- tranzitivita: $\forall x, y, z \in X: xRy \land yRz \implies xRz$

### Ekvivalence a rozkladové třídy

Relace $R$ na $X$ je ekvivalence právě tehdy, když  je symetrická, tranzitivní a reflexivní. Ekivalenční třída prvku $R[x] = \{y \in X | xRy\}$ - obsahuje všechny prvky, které jsou s ním v ekvivalenci.

Z toho vyplývá několik triviálních důsledků:
1. Ekvivalenční třída je neprázdná množina (z reflexivity).
2. Ekvivalenční třída se buď jiné rovná, nebo spolu v průniku nemají žádný prvek.
3. Ekvivalenční třídy určují relaci jednoznačně.

### Částečná uspořádání

#### Základní pojmy (minimální a maximální prvky, nejmenší a největší prvky, řetězec, antiřetězec)

Relace $R$ na $X$ je uspořádání právě tehdy, když je reflexivní, antisymetrická a tranzitivní.

Je několik druhů uspořádání. V lineárním uspořádání jsme schopni všechny prvky mezi sebou porovnat. Částečné uspořádání není lineární (tedy některé, možná všechny) prvky nelze spolu porovnat. Ostré uspořádání známe například >, <.

Minimální prvek je takový prvek, že v nosné množině neexistuje menší. Nejmenší prvek je takový, že všechny prvky musí být porovnatelné s ním a být stejně velké nebo větší (jde tedy o silnější kritérium než u minimality). Obdobně definujeme maximální a největší prvek.

Lexikografické uspořádání je uspořádání postupně podle prvního prvku, pak podle druhého atd (jde třeba o seřazení podle abecedy).

Nechť $(X, \leq)$ je částečně uspořádaná množina (ČUM). Pak platí, že $A \subseteq X$ je řetězec, pokud $\forall a, b \in A$ jsou porovnatelné. Obdobně definujeme antiřetězec $A \subseteq X$, žádné dva prvky nejsou navzájem porovnatelné.

Označujeme $\omega(X, \leq)$ délku nejdelšího řetězce, $\alpha(X, \leq)$ délku nejdelšího antiřetězce.

#### Výška a šířka částečně uspořádané množiny a věta o jejich vztahu (o dlouhém a širokém)

Pro ČUM $(X, \leq)$ platí, že velikost nosné množiny $|X| \leq \alpha \omega$.

### Funkce

Jde o relaci, ve kterém se prvek z $X$ zobrazuje na právě jeden prvek z $Y$. Značíme $f$, podmínku bychom zapsali $\forall x \in X \exists ! y \in Y: x f y$, v matematice také značíme $f: X \rightarrow Y, f(x) = y$.

#### Typy funkcí (prostá, na, bijekce)

Uvažujme funkci $f: X \rightarrow Y$

- být prostá: $\forall x, x' \in X, x \not = x': f(x) \not = f(x')$
- být "na": $\forall y \in Y \exists x \in X: f(x) = y$
- bijekce: prostá a "na", neboli $\forall y \in Y \exists ! x \in X: f(x) = y$

#### Počty různých typů funkcí mezi dvěma konečnými množinami

Mějme funkci $f: A \rightarrow B, a = |A|, b = |B|$. Potom platí, že:
- $|2^X| = 2^{|X|}$
- celkový počet funkcí je $b^a$
- prostých funkcí je $b^{\underline{a}}$ (tedy $\prod_{i=0}^{a-1}(b-i)$)

### Permutace a jejich základní vlastnosti (počet a pevný bod)

Bijekcí pro dvě stejné množiny velikosti $n$ je $n!$.

Bijekcím mezi dvěma stejnými množinami se také říká permutace. Pevný bod permutace je prvek, který se zobrazí sám na sebe ($f(x) = x$).

### Kombinační čísla a vztahy mezi nimi, binomická věta a její aplikace

Nejprve si definujeme kombinační číslo. Jsou k tomu dva způsoby:

${X \choose k} = \{ A \subseteq X | |A| = k \}$, ${n \choose k} = \frac{n!}{k!(n-k)!}$

Druhá definice je používanější. Stejně totiž platí věta $|{X \choose k}| = {|X| \choose k}$.

Teď si uvedeme pár vlastností.
- počet prázdných podmnožin = 1 = počet kompletních podmnožin = ${n \choose n}$
- počet jednoprvkových podmnožin = n = počet podmnožin, kde 1 prvek chybí = ${n \choose n-1} = {n \choose 1}$
- obecně tedy platí ${n \choose k} = {n \choose n-k}$
- počet podmnožin dané množiny: $\sum_{k=0}^n {n \choose k} = 2^n$
- ${n \choose k} = {n - 1 \choose k} + {n - 1 \choose k - 1}$

Dále si definujeme Pascalův trojúhelník, který má řádky indexované od nuly a na každé úrovni má kombinační čísla, kde $n$ je číslo řádku a $k$ postupně zleva roste od nuly až po $n$. Součet řádku je zjevně $2^n$ (viz vzorec nahoře).

Binomická věta: $\forall n \in \mathbb{N}, \forall a, b \in \mathbb{R}: (a+b)^n = \sum_{k=0}^{n} {n \choose k} a^{n-k}b^k$.

Dá se použít třeba v již zmiňovaném Pascalově trojúhelníku, pak pro různé vzorce, součty apod.

### Princip inkluze a exkluze (PIE)

#### Obecná formulace (a důkaz)

Nechť $A_1, ..., A_n$ jsou konečné množiny. Potom platí $|\bigcup_{i=0}^n A_i| = \sum_{k=1}^n (-1)^{k+1} \sum_{I \in {[n] \choose k}} | \bigcap_{i \in I} A_i |$.

Důkaz: Budeme počítat, kolikrát se prvek $x$ nachází nalevo a kolikrát napravo.
Nalevo: 1, protože jde o sjednocení.
Napravo: Předpokládejme, že se vyskytne v $j$ množinách, vyskytuje se tedy v každé $k$-tici z těchto $j$ množin (tedy $k \leq j$). Existuje právě ${j \choose k}$ $k$-prvkových podmnožin $j$-prvkové množiny, ve vzorci se znaménka střídají. Tedy máme ${j \choose 1} - {j \choose 2} + {j \choose 3} + ... + (-1)^{j-1} {j \choose j} = 1$.

#### Použití (problém šatnářky, Eulerova funkce pro počet dělitelů, počet surjekcí)

Problém šatnářky: Pánové přijdou do divadla a odloží své klobouky do šatny. Při odchodu šatnářka vydá každému právě 1 klobouk. Jaká je pravděpodobnost, že žádný pán nedostane svůj klobouk?

Řešení: Obecně se bude řešení blížit k $e^{-1}$.

Eulerova funkce je počet přirozených čísel nesoudělných s $n$, která jsou menší nebo rovna $n$.

Počet surjekcí: Surjekce je jinými slovy to stejné, co je vlastnost funkce "na". Pro výpočet toho, kolik surjekcí existuje, se dá použít právě PIE.

### Hallova věta o systému různých reprezentantů a její vztah k párování v bipartitním grafu

Nejprve definujme, co vlastně systém různých reprezentantů je. Mějme množinový systém $M_i, i \in I$ na množině $X$, platí $M_i \subseteq X$.
Systém různých reprezentantů (SRR) je funkce $f: I \rightarrow X$, která splňuje:
1. $\forall i \in I: f(i) \in M_i$ (z každé z množin zvolí reprezentanta)
2. $f$ je prostá (reprezentant není stejný)

Hallova věta: SRR existuje $\iff \forall J \subseteq I: |\bigcup_{i \in J} M_i| \geq J$.

Důkaz $\implies$: Zvolím libovolně $J \subseteq I$. Pak platí to, že $f$ je prostá, a tím pádem se splnila pravá strana.

Důkaz $\impliedby$: V grafu (jednotkové ohodnocení) najdeme celočíselný maximální tok, tedy tím nalezneme minimální řez. Hrany s tokem 1 dávají SRR.
