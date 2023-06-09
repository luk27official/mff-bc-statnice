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

### Algebraické struktury

#### Grupy a podgrupy, permutace

Buď binární operace na množině $G$, tedy $G^2 \rightarrow G$. Grupa je poté dvojice $(G, \circ)$, která splňuje:
1. Asociativita: $\forall a, b, c \in G: a \circ (b \circ c) = (a \circ b) \circ c$
2. Existence neutrálního prvku: $\exists e \in G \forall x \in G: x \circ e = e \circ x = x$
3. Existence inverzního prvku: $\forall x \in G \exists x' \in G: x \circ x' = x' \circ x = e$
4. Pro tzv. Abelovy grupy ještě platí komutativita: $\forall a, b \in G: a \circ b = b \circ a$

Příklady Abelových grup: $(\mathbb{Z}, +), (\mathbb{Q}, +), (\mathbb{R}, +)$, grupy matic, číselné obory s násobením bez nuly atd. Důležitým případem je konečná grupa $(\mathbb{Z}_n, +)$, kde operace definujeme vždy $mod n$.

Příklad ne-Abelových grup: Zobrazení na množině s operací skládání, permutace...

Platí následující:
1. $a \circ c = b \circ c \implies a = b$
2. neutrální prvek je určen jednoznačně
3. pro každý prvek grupy je jeho inverzní prvek určen jednoznačně
4. $a \circ x = b$ má právě jedno řešení $\forall a, b \in G$
5. $(a^{-1})^{-1} = a$
6. $(a \circ b)^{-1} = b^{-1} \circ a^{-1}$

Podgrupa grupy $(G, \circ)$ je grupa $(H, \diamond)$ taková, že $H \subseteq G$ a pro všechna $a, b \in H$ platí $a \circ b = a \diamond b$. Značíme $(H, \diamond) \leq (G, \circ)$.

Podgrupy jsou uzavřené na průnik, ale ne na sjednocení.

Permutace na konečné množině $X$ je bijekce $p: X \rightarrow X$. Často uvažujeme permutace pro prvky $1, ..., n$. Množina všech permutací pro $n$ prvků se značí $S_n$. Dá se značit například tabulkou, grafem, nebo rozložením na cykly.

Rozložení na cyklus vypadá následovně: $(1, 2)(3)(4, 5, 6)$. Občas se jednoprvkové cykly vynechávají.

Permutace se dají invertovat, skládat apod. Znaménko permutace $sgn(p) = (-1)^{n-k}$.
Permutaci, kde se všechny prvky zobrazí samy na sebe, říkáme identita, permutaci s prohozenými dvěma prvky říkáme transpozice.

#### Tělesa a speciálně konečná tělesa

Těleso je množina $\mathbb{T}$ spolu se dvěma komutativními binárními operacemi sčítání a násobení splňující:
1. $(\mathbb{T}, +)$ je Abelova grupa, neutrální prvek je 0 a inverzní k $a$ je $-a$
2. $(\mathbb{T} \setminus \{0\}, \cdot)$ je Abelova grupa, neutrální prvek je 1 a inverzní k $a$ je $a^{-1}$
3. Distributivita: $\forall a, b, c \in \mathbb{T}: a \cdot (b + c) = a \cdot b + a \cdot c$

Příklady těles jsou třeba $\mathbb{R}, \mathbb{C}$ apod., pozor na to, že množina celých čísel těleso netvoří. Konečná tělěsa $\mathbb{Z}_n$ jsou tělesy pro $n$ prvočíselné.

Základní vlastnosti těles:
1. $0a = 0$
2. $ab = 0 \implies a = 0 \lor b = 0$
3. $-a = (-1)a$

Charakteristika tělesa je nejmenší počet jedniček, které při sečtení dají 0. Pokud takové číslo neexistuje, pak se definuje jako 0.

### Soustavy lineárních rovnic

#### Maticový zápis, elementární řádkové úpravy, odstupňovaný tvar matice

Matice typu $m \times n$ je obdélníkové schéma (tabulka) reálných čísel, značíme ji $A$ a pro $m = n$ je matice čtvercová. Jednotlivé prvky indexujeme často písmeny $i, j$, poté je prvek na řádku $i$ a ve sloupci $j$ značen $a_{ij}$ nebo $A_{ij}$.

Sloupcový vektor je matice typu $n \times 1$, řádkový vektor $1 \times n$.

Hvězdičkovou notací značíme výběr jednoho celého řádku, popřípadě sloupce.

Maticí soustavy rozumíme $(A | b)$, kde matice $A$ obsahuje koeficienty proměnných a sloupec vpravo hodnoty na pravé straně soustavy.

Matice lze upravovat přes elementární řádkové úpravy:
1. vynásobení $i$-tého řádku reálným nenulovým číslem
2. přičtení $\alpha$-násobku $j$-tého řádku k $i$-tému ($\alpha \in \mathbb{R}, i \not = j$)
3. výměna $i$-tého a $j$-tého řádku

Tyto úpravy zachovávají množinu řešení soustavy.

Matice je v řádkově odstupňovaném tvaru (REF), pokud existuje $r$ takové, že platí:
1. řádky $1, ..., r$ jsou nenulové
2. řádky $r + 1, ..., m$ jsou nulové
3. označíme-li $p_i = \min\{j, a_{ij} \not = 0\}$ pozici (pivot) prvního nenulového prvku v $i$-tém řádku, pak $p_1 < p_2 < ... < p_r$

Dalším pojmem, který se nám hodí, je tzv. hodnost matice, to je počet nenulových řádků po převodu matice do tvaru REF.

Převod matice do REF můžeme udělat pomocí řádkových elementárních úprav.

#### Gaussova a Gaussova-Jordanova eliminace, popis množiny řešení

Gaussova eliminace se provádí převodem matice $A$ do REF tvaru, po převodu může nastat následující:
1. soustava nemá řešení, pokud na pravé straně matice (v $b$) je pivot
2. soustava má právě jedno řešení, pokud počet proměnných je roven počtu pivotů, který není napravo
3. soustava má nekonečně mnoho řešení, pokud počet proměnných je vyšší než počet pivotů

Gaussova-Jordanova eliminace funguje stejně, až na to, že se převádí do tvaru RREF, který zajišťuje, že na pozicích pivotů jsou jedničky a nad každým pivotem jsou pouze nuly. Řešení fungují obdobně. Převod na RREF tvar je jednoznačný.

### Matice

Definice matice viz nahoře, už jsme ji potřebovali.

#### Operace s maticemi a základní typy matic, hodnost matice

Rovnost matic nastává při stejných rozměrech a hodnotách na každé pozici.

Součet matic definujeme pro každý prvek jako součet prvků na dané pozici, rozdíl obdobně.

Násobek matice s číslem definujeme pro každý prvek jako $(\alpha A)_{ij} = \alpha A_{ij}$.

Platí komutativita, asociativita, distributivita, pravidla $A + 0 = A, 1A = A, A + (-1)A = 0, \alpha(\beta A) = (\alpha\beta)A$.

Součin dvou matic definujeme pro $A \in \mathbb{R}^{m \times p}, B \in \mathbb{R}^{p \times n}$ jako $AB$, což bude matice typu $\mathbb{R}^{m \times n}$ s prvky $(AB)_ij = \sum_{k=1}^p A_{ik} B_{kj}$. Pomůcka - prvek na pozici $(i, j)$ spočítáme jako skalární součin $i$-tého řádku matice $A$ a $j$-tého sloupce matice $B$.

Definujme si jednotkovou matici $I_n$ jako matici $n \times n$, která má na diagonále jedničky, všude jinde nuly. Obdobně se definuje nulová matice, která má všude nuly (někdy $0_n$). 

Součin dvou matic je asociativní, distributivní zprava i zleva, pronásobení číslem lze z libovolné strany a násobení jednotkovou a nulovou maticí funguje tak, jak bychom očekávali. Pozor na to, že součin dvou matic není komutativní, tedy $AB \not = BA$ pro mnoho matic!

Transpozici matice značíme $A^T$ a jde o překlopení podle hlavní diagonály, tedy sloupce uvažujeme jako řádky a vice versa.

Platí například $(A^T)^T = A, (A + B)^T = A^T + B^T, (\alpha A)^T = \alpha A^T, (AB)^T = B^T A^T$.

Matice je symetrická, pokud $A = A^T$.

Další typy matic:
- diagonální matice: všechny prvky mimo diagonálu jsou nulové
- horní trojúhelníková matice: všechny prvky pod diagonálou (mimo diagonálu) jsou  nulové
- dolní trojúhelníková matice: všechny prvky nad diagonálou (mimo diagonálu) jsou nulové

Hodnost matice jsme si již definovali.

#### Regulární a inverzní matice

Matice $A$ je regulární, pokud soustava $Ax = 0$ má jediné řešení $x = 0$. V opačném případě se matice nazývá singulární.

$A \in \mathbb{R}^{n \times n}$ je regulární právě tehdy, když RREF tvar matice je jednotková matice a hodnost matice je rovna počtu řádků. Regulární matice mají navíc jedno řešení pro každou soustavu rovnic.

Součin regulárních matic je také regulární matice, součin singulární a libovolné matice je matice singulární. Je-li matice regulární, pak je její transpozice taky regulární.

Každá regulární matice se dá vyjádřit jako součin konečně mnoha elementárních matic.

Inverzní matice pro $A \in \mathbb{R}^{n \times n}$ je $A^{-1}$, pokud platí $AA^{-1} = A^{-1}A = I_n$. Inverzní matice existuje pro regulární matice.

Pro regulární matice ještě platí $(A^{-1})^T = (A^T)^{-1}, (A^{-1})^{-1} = A, (\alpha A)^{-1} = \frac{1}{\alpha} A^{-1} (\alpha \not = 0), (AB)^{-1} = B^{-1} A^{-1}$.

### Vektorové prostory

#### Vektorový prostor a podprostor, lineární obal, lineární kombinace, generátory

Buď $\mathbb{T}$ těleso s neutrálními prvky 0 pro sčítání a 1 pro násobení. Poté vektorovým prostorem nad tělesem $\mathbb{T}$ rozumíme množinu $V$ s operacemi sčítání vektorů $+: V^2 \rightarrow V$ a násobení vektroů skalárem $\mathbb{T} \times V \rightarrow V$ splňující pro každé $\alpha, \beta \in \mathbb{T}, u, v \in V$:
1. $(V, +)$ je Abelova grupa, neutrální prvek značíme $0$, inverzní k $v$ značíme $-v$
2. asociativita: $\alpha(\beta v) = (\alpha \beta) v$
3. $1v = v$
4. distributivita: $(\alpha+\beta)v = \alpha v + \beta v$
5. distributivita: $\alpha(u + v) = \alpha u + \alpha v$

Prvky vektorového prostoru značíme písmeny a říkáme jim vektory. Prvkům tělesa $\mathbb{T}$ říkáme skaláry.

Příklad vektorových prostorů: $\mathbb{R}^n$ nad $\mathbb{R}$, $\mathbb{T}^n$ nad $\mathbb{T}$, prostor matic $\mathbb{R}^{m \times n}$ nad $\mathbb{R}$, ...

Buď $V$ vektorový prostor nad $\mathbb{T}$, pak $U \subseteq V$ je podprostorem $V$, pokud také tvoří vektorový prostor nad $\mathbb{T}$ se stejnými operacemi. Značíme $U \Subset V$.

Podprostor musí obsahovat nulový vektor a být uzavřený na součet a násobení. Průnik podprostorů je také podprostor původního prostoru.

Buď $V$ vektorový prostor nad $\mathbb{T}$ a $W \subseteq V$. Pak lineární obal $W$, značený $span(W)$, je průnik všech podprostorů $V$ obsahujících $W$.

Nechť prostor U je lineárním obalem množiny vektorů $W$, tedy $U = span(W)$, pak říkáme, že $W$ generuje prostor $U$ a prvky množiny $W$ jsou generátory $U$. Prostor $U$ je konečně generovaný, pokud je generovaný nějakou konečnou množinou vektorů.

Lineární kombinace: Buď $V$ vektorový prostor nad $\mathbb{T}$ a $v_1, ..., v_n \in V$. Pak lineární kombinací vektorů $v_1, ..., v_n$ rozumíme výraz typu $\sum_{i=1}^n \alpha_i v_i = \alpha_1 v_1 + ... + \alpha_n v_n$, kde $\alpha_1, ..., \alpha_n \in \mathbb{T}$. Lineární obal pak obsahuje všechny lineární kombinace generátorll.

#### Lineární závislost a nezávislost, báze a její existence, souřadnice, dimenze

Buď $V$ vektorový prostor na $\mathbb{T}$ a mějme vektory $v_1, ..., v_n \in V$. Pak tyto vektory nazýváme lineárně závislé, pokud rovnost $\sum_{i=1}^n \alpha_i v_i = o$ nastane pouze pro $\alpha_1, ..., \alpha_n = 0$. V opačném případě jsou vektory lineárně závislé.

Buď $V$ vektorový prostor nad $\mathbb{T}$ a $M \subseteq V$ nekonečná množina vektorů. Pak je $M$ lineárně nezávislá, pokud každá konečná podmnožina $M$ je lineárně nezávislá. V opačném případě je $M$ lineárně závislá.

Například sloupce, resp. i řádky regulární matice jsou lineárně nezávislé.

Uvažujme vektorový prostor $V$ nad $\mathbb{T}$, pak bází rozumíme libovolný lineárně nezávislý systém generátorů $V$. Každý vektorový prostor dokážeme vyjádřit tzv. kanonickou bazí, která obsahuje vektory $e_1, ..., e_n$, kde na pozici indexu vektor obsahuje jedničku, jinde nuly.

Nechť $B = \{ v_1, ..., v_n \}$ je báze prostoru $V$ a nechť $u \in V$ má nějaké vyjádření $u = \sum_{i=1}^n \alpha_i v_i$. Pak souřadnicemi vektoru $u \in V$ vzhledem k bázi $B$ rozumíme koeficienty $\alpha_1, ..., \alpha_n$, vektor souřadnic značíme $[u]_B = (\alpha_1, ..., \alpha_n)^T$.

Každý vektorový prostor má bázi, všechny báze nějakého vektorového prostoru jsou stejně velké.

Steinitzova věta o výměně: Buď $V$ vektorový prostor, $x_1, ..., x_m$ lineárně nezávislý systém ve $V$, nechť $y_1, ..., y_n$ je systém generátorů $V$. Platí:
1. $m \leq n$
2. existují navzájem různé indexy $k_1, ..., k_{n - m}$ takové, že $x_1, ..., x_m, y_{k_1}, ..., y_{k_{n-m}}$ tvoří systém generátorů $V$.

Dimenze konečně generovaného vektorového prostoru je velikost nějaké jeho báze. Značíme $\dim V$. Dimenze podprostoru je menší rovna dimenzi samotného prostoru.

Obecně ještě platí, že každý lineárně nezávislý systém lze rozšířit na bázi.

#### Maticové podprostory (řádkový, sloupcový, jádro)

Definujme podprostory:
1. sloupcový prostor $\mathcal{S}(A) = span\{A_{*1}, ..., A_{*n}\} = \{Ax; x \in \mathbb{T}^n \}$
2. řádkový prostor $\mathcal{R}(A) = \mathcal{S}(A^T) = \{A^Ty; y \in \mathbb{T}^m \}$
3. jádro $Ker(A) = \{ x \in \mathbb{T}^n; Ax = o \}$

Sloupcový prostor je tedy prostor generovaný sloupci matice a je to podprostor $\mathbb{T}^m$. Obdobně řádkový prostor je generovaný řádky matice a je to podprostor $\mathbb{T}^n$. Jádro je tvořeno všemi řešeními soustavy $Ax = o$, takže obsahuje nulový vektor, je uzavřené na součty a násobky.

Platí $\dim Ker(A) + rank(A) = n$.

### Lineární zobrazení

#### Definice, maticová reprezentace lineárního zobrazení, matice složeného zobrazení

Buďte $U, V$ vektorové prostory nad $\mathbb{T}$. Zobrazení $f: U \rightarrow V$ je lineární, pokud $\forall x, y \in U, \alpha \in \mathbb{T}$ platí:
1. $f(x + y) = f(x) + f(y)$
2. $f(\alpha x) = \alpha f(x)$

Lineárnímu zobrazení také říkám homomorfismus.

Lineární zobrazení reprezentujeme maticově, můžeme využít předpis $x \rightarrow Ax$.

Příklad zobrazení je třeba identita, matice rotace, apod.

Matice rotace = $\begin{pmatrix}
\cos(\alpha) & -\sin(\alpha)\\
\sin(\alpha) & \cos(\alpha)
\end{pmatrix}$

Buď $f: U \rightarrow V$ lineární zobrazení. Pak platí:
1. $f(\sum_{i=1}^n \alpha_i x_i) = \sum_{i=1}^n \alpha_i f(x_i)$
2. $f(o) = o$

Dále definujeme:
1. obraz $f(U) = \{ f(x); x \in U \}$
2. jádro $Ker(f) = \{ x \in U; f(x) = o \}$
3. $f(U)$ je podprostorem $V$
4. $Ker(f)$ je podprostorem $U$

Pokud je zobrazení prosté, pak jádro obshauje pouze nulový vektor a obraz libovolné lineárně nezávislé množiny je lineárně nezávislá množina.

Buďte $U, V$ prostory nad $\mathbb{T}$ a $x_1, ..., x_n$ báze $U$, pro libovolné vektory $y_1, ..., y_n \in V$ existuje právě jedno lineární zobrazení takové, že $f(x_i) = y_i$.

Buď $f: U \rightarrow V$ lineární zobrazení, $B_U = \{ x_1, ..., x_n \}$ báze prostoru $U$, $B_V = \{ y_1, ..., y_m \}$ báze prostoru $V$. Nechť $f(x_j) = \sum_{i=1}^m a_{ij}y_i$. Potom matice $A \in \mathbb{T}^{m \times n}$ s prvky $a_{ij} = 1, ..., m; j = 1, ..., n$ se nazývá matice lineárního zobrazení vzhledem k bázím $B_U, B_V$ a značíme ji ${}_{B_V} [f]_{B_U}$. Matice lineárního zobrazení vypadá tak, že její $j$-tý sloupce je tvořen souřadnicemi obrazu vektoru $x_j$ vzhledem k bázi $B_V$.

Maticová reprezentace lineárního zobrazení: Buď $f: U \rightarrow V$ lineární zobrazení a báze jak jsme definovali nahoře. Pak $\forall x \in U: [f(x)]_{B_V} = {}_{B_V}[f]_{B_U} \cdot [x]_{B_U}$.

Každé lineární zobrazení se dá definovat jako matice, nahlédneme přes kanonické báze. Takové zobrazení je jednoznačné.

Matice přechodu je matice, která vyjadřuje převod vektorů z jedné báze do druhé. Pro podmínky viz nahoře platí $[x]_{B_U} = {}_{B_U}[id]_{B_V} \cdot [x]_{B_V}$.

Matici přechodu můžeme spočítat tak, že dáme vektory báze $B_V$ na levou stranu matice, vektory báze $B_U$ na pravou stranu a upravíme do RREF tvaru. Nalevo dostaneme jednotkovou matici a napravo dostaneme matici přechodu ${}_{B_V}[id]_{B_U}$.

Lineární zobrazení můžeme skládat. Takové zobrazení je také lineární. Matici složeného lineárního zobrazení můžeme zapsat následovně pro $f: U \rightarrow V, g: V \rightarrow W$ a jejich příslušné báze $B$ s odpovídajícím indexem: ${}_{B_W}[g \circ f]_{B_U} = {}_{B_W}[g]_{B_V} \cdot {}_{B_V}[f]_{B_U}$.

#### Obraz a jádro lineárních zobrazení

Viz nahoře, už jsme to potřebovali.

Platí různé rovnosti o dimenzích, důležitá je například $\dim U = \dim Ker(f) + \dim f(U)$.

Dále platí, že $f$ je prosté právě tehdy, když má matice lin. zobrazení lineárně nezávislé sloupce. Zobrazená je "na" právě tehdy, když má matice lin. zobrazení lineárně nezávislé řádky.

#### Isomorfismus prostorů

Isomorfismus mezi prostory $U, V$ nad $\mathbb{T}$ je vzájemně jednoznačné lineární zobrazení $f: U \rightarrow V$. Pokud mezi těmito dvěma prostory existuje isomorfismus, pak jsou isomorfní.

Platí také následující:
1. Inverzní isomorfismus existuje a je to také isomorfismus.
2. Isomorfismus je tranzitivní.
3. Lineární zobrazení $f: U \rightarrow V$ je isomorfismem právě tehdy, když libovolná báze prostoru $U$ se zobrazuje na bázi $V$. Z toho také vyplývá $dim(U) = dim(V)$.

### Skalární součin

#### Skalární součin, norma indukovaná skalárním součinem

Standardní skalární součin vektorů $x, y \in \mathbb{R}^n$ je definován jako $x^Ty = \sum_{i=1}^n x_i y_i$. Euklidovská norma vektoru (neboli velikost) je definována jako $||x|| = \sqrt{x^Tx} = \sqrt{\sum_{i=1}^n x^2_i}$. Platí, že norma je nezáporná. Geometricky skalární součin vyjadřuje vztah $x^Ty = ||x|| \cdot ||y|| \cdot \cos(\varphi)$. Z toho vyplývá, že vektory jsou kolmé, právě když je skalární součin vektorů nulový.

Skalární součin je symetrický a lineární funkcí v první i druhé složcee, ale ne v obou zároveň.

Buď $V$ vektorový prostor nad $\mathbb{R}$. Pak skalární součin je zobrazení $\langle \cdot, \cdot \rangle: V^2 \rightarrow \mathbb{R}$ splňující pro všechna $x, y, z \in V, \alpha \in \mathbb{R}$:
1. $\langle x, x\rangle \geq 0$ a rovnost nastene pouze pro $x = 0$
2. $\langle x + y, z \rangle = \langle x, z \rangle + \langle y, z \rangle$
3. $\langle \alpha x, y \rangle = \alpha \langle x, y \rangle$
4. $\langle x, y \rangle = \langle y, x \rangle$

Pro komplexní čísla platí to stejné, jen v posledním (4.) důsledku musíme uvažovat komplexně sdružené číslo!

Standardní skalární součin bězně používáme při maticovém násobení. Každý kladný násobek standardního skalárního součinu je také skalárním součinem.

Podobně jako u lineárního zobrazení, i skalární součin je určen jednoznačně.

Norma indukovaná skalárním součinem: $||x|| = \sqrt{\langle x, x \rangle}$, kde $x \in V$.

Ještě si definujme normu obecně: Buď $V$ vektorový prostor nad reálnými nebo komplexními čísly. Pak je norma zobrazení $|| \cdot ||: V \rightarrow \mathbb{R}$ splňující:
1. $\forall x \in V: ||x|| \geq 0$ a rovnost pouze pro nulový vektor
2. $\forall x \in V, \forall \alpha \in \mathbb{C}: ||\alpha x|| = | \alpha | \cdot || x ||$
3. $||x + y|| \leq || x || + || y ||$

Normu pro spojité funkce definujeme přes integrál.

Metrika na množině $M$ je zobrazení $d: M^2 \rightarrow \mathbb{R}$, jde o normu rozdílu vektorů. Jedná se o vzdálenost. Je také nezáporná, symetrická a platí pro ni trojúhelníková nerovnost.

#### Pythagorova věta, Cauchyho-Schwarzova nerovnost, trojúhelníková nerovnost

Pythagorova věta: $||x||^2 + ||y||^2 = ||x + y||^2$, pokud jsou $x, y$ kolmé.

Cauchy-Schwarzova nerovnost: $\forall x, y \in V: |\langle x, y \rangle| \leq ||x|| \cdot ||y||$

Trojúhelníková nerovnost: $\forall x, y \in V: ||x + y|| \leq ||x|| + ||y||$

#### Ortonormální systémy vektorů, Fourierovy koeficienty, Gramova-Schmidtova ortogonalizace

Systém vektorů je ortogonální, pokud je skalární součin dvou libovolných vektorů ze systému roven nule (tedy jsou na sebe všechny vektory kolmé). Systém je ortonormální, právě tehdy když je ortogonální a zároveň platí $|| z_i || = 1$ pro všechny vektory systému. Je-li systém ortogonální, pak se dá jednoduše zortonormalizovat, prostě pronásobíme vektory nějakou konstantou.

Je-li systém vektorů $z_1, ..., z_n$ ortonormální, pak je lineárně nezávislý. To lze nahlédnout z definice lineární kombinace.

Fourierovy koeficienty: Buď $z_1, ..., z_n$ ortonormální báze prostoru $V$. Pak pro každé $x \in V$ platí $x = \sum_{i = 1}^n \langle x, z_i \rangle z_i$. Tomuhle říkáme Fourierův rozvoj a skaláry se nazývají Fourierovy koeficienty.

Gramova-Schmidtova ortogonalizace začne s libovolnou bazí a postupně nakolmuje vektory, vytváří bázi, která je ortonormální. Nakolmování funguje tak, že v jedné fázi odečteme od vektoru $x_k$ jeho projekci do prostoru generovaného předchozími vektory, takže bude kolmý i na ty předchozí. Poznámka: Tady bych asi opět doporučil se podívat na nějaký konkrétní příklad, pamatovat si ten algoritmus je celkem těžké, ale v praxi to je celkem intuitivní.

Každý konečně generovaný prostor se skalárním součinem má svou ortonormální bázi.

### Ortogonální doplněk, ortogonální projekce, projekce jako lineární zobrazení

Buď $V$ vektorový prostor a $M \subseteq V$. Pak ortogonální doplněk množiny $M$ je $M^{\perp} = \{ x \in V; \langle x, y \rangle = 0 \forall y \in M \}$. Tedy je to doplňek podprostoru $M$ takový, že všechny vektory z $M^{\perp}$ jsou kolmé na vektor z $M$.

Platí, že ortogonální doplněk je také podprostorem $V$, že $M^{\perp} = span(M)^{\perp}$ a je-li $M \subseteq N$, pak platí obrácená inkluze pro doplňky.

Dále platí, že $M \cap M^{\perp} = \{ o \}, V = U + U^{\perp}, (U^{\perp})^\perp = U,  \dim V = \dim U + \dim U^{\perp}$.

Ortogonální projekce: Buď $V$ vektorový prostor a $U$ jeho podprostor. Pak projekcí vektoru $x \in V$ do $U$ rozumíme takový vektor $x_U \in U$, který splňuje $||x - x_U|| = \min_{y \in U} ||x - y||$. Vektor $y$ je určen jednoznačně (z Pythagorovy věty).

Doplňěk řádkového podprostoru matice $A$ je roven jeho jádru. Platí také:
1. $Ker(A^T A) = Ker(A)$
2. $\mathcal{R}(A^T A) = \mathcal{R}(A)$
3. $rank(A^T A) = rank(A)$

Ortogonální projekce: Buď $A \in \mathbb{R}^{m \times n}$ hodnosti $n$. Pak projekce vektoru $x \in \mathbb{R}^m$ do sloupcového prostoru je $x' = A(A^T A)^-1 A^T x$.

Matice $P$ je matice projekce právě tehdy, když je symetrická a $P = P^2$.

Matici projekce do doplňku získáme tak, že matici projekce odečteme od jednotkové matice.

#### Ortogonální matice a jejich vlastnosti

Matice $\mathbb{Q} \in \mathbb{R}^{n \times n}$ je ortogonální, pokud $Q^T Q = I_n$. Matice $\mathbb{Q} \in \mathbb{C}^{n \times n}$ je unitární, pokud $\overline{Q}^T Q = I_n$.

Následující tvrzení jsou ekvivalentní:
1. $Q$ je ortogonální
2. $Q$ je regulární a $Q^{-1} = Q^T$
3. $QQ^T = I_n$
4. $Q^T$ je ortogonální
5. $Q^{-1}$ existuje a je ortogonální
6. sloupce i řádky $Q$ tvoří ortonormální bázi $R^n$

Součin ortogonálních matic je také ortogonální matice.

Příklady: jednotková matice, Householderova matice, Givensova matice (například matice rotace)

Dále pro ortogonální matice platí:
1. $\langle Qx, Qy \rangle = \langle x, y \rangle$ pro každé $x, y \in \mathbb{R}^n$
2. $\forall x \in \mathbb{R}^n: ||Qx|| = ||x||$
3. prvky ortogonální matice mají hodnoty mezi 0 až 1 včetně, to platí i pro inverzi
4. $\begin{pmatrix}
1 & o^T\\
o & Q
\end{pmatrix}$ je také ortogonální matice.

Ortogonální matice a lineární zobrazení: Buďte $U, V$ prostory nad $\mathbb{R}$ s libovolným skalárním součinem a $f: U \rightarrow V$ lineární zobrazení. Nechť $B_U, B_V$ jsou ortonormální báze U a V. Pak matice zobrazení ${}_{B_V}[f]_{B_U}$ je ortogonální právě tehdy, když $\langle f(x), f(y) \rangle = \langle x, y \rangle$ pro každé $x, y \in U$.

Poslední definice, která se k tomuto tématu vztahuje, je stopa matice $trace(A) = \sum_{i=1}^n x_{ii}$, tedy součet prvků na diagonále.

### Determinanty

#### Definice a základní vlastnosti determinantu (multiplikativnost, determinant transponované matice, vztah s regularitou a vlastními čísly)

Buď $A \in \mathbb{T}^{n \times n}$. Pak determinant matice je $det(A) = \sum_{p \in S_n}sgn(p)\prod_{i=1}^n a_{i, p(i)}$. Značíme buď $det(A)$ nebo $|A|$.

Pro matice řádu 2 je determinant roven součinu diagonály mínus součin antidiagonály. Pro matice řádu 3 je determinant podobný, jde o součet součinů diagonál mínus součet součinů antidiagonál. Pro větší matice neexistuje nějaký jednoduchý vzorec, obecně je celkem náročné počítat determinanty, protože výpočtů je řádově $n!$.

Pro horní trojúhelníkovou matici je determinant roven součinu prvků na diagonále.

Platí $det(A^T) = det(A)$. Obecně neplatí třeba $det(A + B) = det(A) + det(B)$, ale platí řádková a sloupcová linearita.

Jak se mění determinant s řádkovými úpravami?
1. Při vynásobení nějakého řádku skalárem $\alpha \in \mathbb{T}$ se i determinant zvětší $\alpha$-krát.
2. Výměna dvou řádků změní znaménko determinantu ($det(A') = -det(A)$).
3. Přičtení násobku některého řádku k jinému determinant nemění.

Pokud má matice dva stejné řádky, pak je $det(A) = 0$. Obecně platí, že matice je regulární právě tehdy, když je determinant nenulový.

Multiplikativnost determinantu: Pro každé dvě matice $A, B \in \mathbb{T}^{n \times n}$ platí $det(AB) = det(A) det(B)$. Z toho vyplývá například i to, že pro $A$ regulární platí $det(A^{-1}) = det(A)^{-1}$.

Inverze matice má celočíselné hodnoty právě tehdy, když $det(A) = \pm 1$.

Vztah s vlastními čísly bude zmíněn v kapitole o vlastních číslech a vektorech.

#### Laplaceův rozvoj determinantu

Laplaceův rozvoj podle $i$-tého řádku: Buď $A \in \mathbb{T}^{n \times n}, n \geq 2$. Pak pro každé $i = 1, ..., n$ platí $det(A) = \sum_{j=1}^n (-1)^{i+j} a_{ij} det(A^{ij})$, kde matice $A^{ij}$ je matice po vyškrtnutí $i$-tého řádku a $j$-tého sloupce. Dá se rozvíjet podle libovolného řádku i sloupce.

#### Geometrická interpretace determinantu

Determinant má několik geometrických významů, uvažujeme-li lineární zobrazení s maticí $A \in \mathbb{R}^{n \times n}$, pak geometrická tělesa mění v tomto zobrazení svůj objem s koeficientem $|det(A)|$. Objem tady není myšlen jen jako klasický trojrozměrný, v $\mathbb{R}^2$ jde o obsah apod.

Dále determinant může posloužit k výpočtu objemu rovnoběžnostěnu. Buď $A \in \mathbb{R}^{m \times n}$ a uvažujme rovnoběžnostěn s hranami danými řádky matice $A$. Pak jeho objem (opět ve smyslu objemu dané dimenze) je roven $\sqrt{det(AA^T)}$. Speciálně pro $m = n$ je objem $|det(A)|$.

### Vlastní čísla a vlastní vektory

#### Definice, geometrický význam a základní vlastnosti vlastních čísel, charakteristický polynom, násobnost vlastních čísel

Buď $A \in \mathbb{C}^{n \times n}$. Pak $\lambda \in \mathbb{C}$ je vlastní číslo matice $A$ a $x \in \mathbb{C}^n$ je vlastní vektor, pokud platí $Ax = \lambda x, x \not = o$. Nenulovost vektoru $x$ je nezbytná podmínka, jinak by byla rovnice splněna triviálně pro každé $\lambda$.

Vlastní vektor reprezentuje invariantní směr při zobrazení $x \rightarrow Ax$, tedy směr, který se zobrazí opět na ten samý směr.

Buď $A \in \mathbb{C}^{n \times n}$. Pak:
1. $\lambda \in \mathbb{C}$ je vlastním číslem právě tehdy, když $det(A - \lambda I_n) =  0$
2. $x \in \mathbb{C}^n$ je vlastním vektorem příslušným k vlastnímu číslu $\lambda \in \mathbb{C}$ právě tehdy, když $o \not = x \in Ker(A - \lambda I_n)$.

Nechť $A \in \mathbb{C}^{n \times n}$ je trojúhelníková matice. Pak její vlastní čísla jsou prvky na diagonále.

Charakteristický polynom matice $A \in \mathbb{C}^{n \times n}$ vzhledem k proměnné $\lambda$ je $p_A(\lambda) = det(A - \lambda I_n) = (-1)^n \lambda^n + a_{n-1} \lambda^{n-1} + ... + a_1 \lambda + a_0$.

Kořeny takového polynomu odpovídají vlastním číslům matice $A$. Takových kořenů je $n$ včetně jejich násobností. Algebraická násobnost značí násobnost $\lambda$ jako kořen char. polynomu, geometrická násobnost $\lambda$ je rovna $n - rank(A - \lambda I_n)$, tedy počtu lineárně nezávislých vlastních vektorů odpovídajících $\lambda$.

Platí, že pro $A \in \mathbb{C}^{n \times n}$ s vlastními čísly $\lambda_1, ..., \lambda_n$ a vlastními vektory $x_1, x_2, ..., x_n$:
1. $det(A) = \lambda_1 \lambda_2 ... \lambda_n$
2. $trace(A) = \lambda_1 + \lambda_2 + ... + \lambda_n$
3. $A$ je regulární právě tehdy, když 0 není její vlastní číslo
4. je-li $A$ regulární, pak $A^{-1}$ má vlastní čísla $\lambda_1^{-1}, \lambda_2^{-1} ...$ a vlastní vektory stejné jako původní matice
5. $A^2$ má vlastní čísla $\lambda_1^2, ..., \lambda_n^2$ a vlastní vektory $x_1, ..., x_n$
6. $\alpha A$ má vlastní čísla $\alpha \lambda_1, ..., \alpha \lambda_n$ a vlastní vektory $x_1, ..., x_n$
7. $A + \alpha I_n$ má vlastní čísla $\lambda_1 + \alpha, ... \lambda_n + \alpha$ a vlastní vektory $x_1, ..., x_n$
8. $A^T$ má vlastní čísla $\lambda_1, ..., \lambda_n$, ale vlastní vektory obecně jiné.

Je-li $\lambda$ vlastní číslo matice, pak je i komplexně sdružené $\overline{\lambda}$ číslo vlastním číslem téže matice.

Spektrum matice $A$ je množina jejích vlastních čísel $\{\lambda_1, ..., \lambda_n\}$, spektrální poloměr je maximum z absolutních hodnot spektra.

#### Podobnost a diagonalizovatelnost matic, spektrální rozklad

Matice $A, B \in \mathbb{C}^{n \times n}$ jsou si podobné, existuje-li regulární matice $S \in \mathbb{C}^{n \times n}$ taková, že $A = S B S^{-1}$. Podobné matice mají stejná vlastní čísla. Počet lineárně nezávislých vlastních vektorů se také nezmění.

Matice $A \in \mathbb{C}^{n \times n}$ je diagonalizovatelná, pokud je podobná nějaké diagonální matici. Diagonální matice obecně značíme $\Lambda$. Matice $A$ je diagonalizovatelná právě tehdy, když má $n$ lineárně nezávislých vlastních vektorů.

Různá vlastní čísla mají lineárně nezávislé vlastní vektory. Pokud má matice $A \in \mathbb{C}^{n \times n}$ $n$ navzájem různých vlastních čísel, pak je diagonalizovatelná.

Pokud máme 2 matice $A, B$, pak mají matice $AB$ i $BA$ stejná vlastní čísla včetně násobností.

Takový rozklad se mimochodem hodí třeba pro mocnění matice.

#### Symetrické matice, jejich vlastní čísla a spektrální rozklad

Hermitovská transpozice matice $A \in \mathbb{C}^{n \times n}$ je matice $A^* = \overline{A}^T$. Matice je hermitovská, pokud platí $A^* = A$. Symetrická matice je to stejné, ovšem pouze pro reálná čísla.

Vlastní čísla reálných symetrických i hermitovských matic jsou reálná.

Pro každou symetrickou matici $A \in \mathbb{R}^{n \times n}$ existuje ortogonální $Q \in \mathbb{R}^{n \times n}$ a diagonální $\Lambda \in \mathbb{R}^{n \times n}$ takové, že $A = Q \Lambda Q^T$.

### Positivně semidefinitní a positivně definitní matice

#### Charakterizace a vlastnosti, vztah se skalárním součinem, vlastními čísly

Buď $A \in \mathbb{R}^{n \times n}$ symetrická. Pak $A$ je positivně semidefitní, pokud $x^TAx \geq 0$ pro všechna $x \in \mathbb{R}^n$, positivně definitní, pokud $x^TAx > 0$ pro všechna $x \not = o$. Positivní definitnost je tedy slabší než semidefinitnost.

Nesymetrické matice můžeme zesymetrizovat úpravou $\frac{1}{2}(A + A^T)$.

Příkladem positivně semidefinitní (PSD) matice je nulová matice, příkladem positivně definitní (PD) matice je jednotková matice.

PSD matice mají nezápornou diagonálu, PD mají kladnou diagonálu.

Platí následující:
1. Jsou-li dvě matice $A, B \in \mathbb{R}^{n \times n}$ PD, pak i jejich součet je PD
2. Je-li $A \in \mathbb{R}^{n \times n}$ PD a $\alpha > 0$, pak je i $\alpha A$ PD
3. Je-li $A \in \mathbb{R}^{n \times n}$ PD, pak je regulární a i $A^{-1}$ je PD

Buď $A \in \mathbb{R}^{n \times n}$ symetrická. Pak $A$ je PSD, vlastní čísla $A$ jsou nezáporná a existuje $U \in \mathbb{R}^{n \times n}$ taková, že $A = U^T U$.

Gramova matice $G \in \mathbb{R}^{m \times m}$, která je definována jako $G_{ij} = \langle w_i, w_j \rangle$, kde $w_1, ..., w_n$ jsou generátory daného podprostoru a závorky reprezentují skalární součin. Pak platí, že Gramova matice je PSD (to vyplývá z toho, že skalární součin je nezáporný). Pokud generátory tvoří bázi, pak je Gramova matice PD.

Positivní (semi)definitnost se testuje rekurentně nebo přes Sylvestrovo kritérium. V požadavcích to není, pro jistotu by bylo dobré se podívat na nějaké příklady.

Operace $\langle x, y \rangle$ je skalárním součinem v $\mathbb{R}^n$ právě tehdy, když má tvar $\langle x, y \rangle = x^TAy$ pro nějakou PD matici $A \in \mathbb{R}^{n \times n}$.

Pro každou PSD matici $A \in \mathbb{R}^{n \times n}$ existuje PSD matice $B \in \mathbb{R}^{n \times n}, B^2 = A$. To vyplývá z toho, že existuje spektrální rozklad pro takovou matici $A$.

Aplikace PD/PSD matic jsou například v optimalizačních problémech, určování struktury bílkovin apod.

#### Choleského rozklad (znění věty a praktické použití)

Pro každou PD matici $A \in \mathbb{R}^{n \times n}$ existuje jedna dolní trojúhelníková matice $L \in \mathbb{R}^{n \times n}$ s kladnou diagonálou taková, že $A = LL^T$.

Existuje opět nějaký algoritmus pro výpočet, nemyslím, že to bude potřeba. Choleského rozklad je výhodný například proto, že dokáže ověřit PD/PSD matice v řádově nejméně krocích.

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
