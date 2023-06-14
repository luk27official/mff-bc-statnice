# Společná informatika

## Automaty a jazyky

Obecně si definujme nějaké pojmy:
- množina symbolů $\Sigma$ (abeceda)
- slovo je konečná (i prázdná) posloupnost symbolů $s \in \Sigma$, prázdné slovo značíme $\lambda$ nebo $\epsilon$
- množina všech slov v abecedě je $E^*$
- množina všech neprázdných slov v abecedě je $E^+$
- jazyk je $L \subseteq E^*$
- operace se slovy $u, v \in L$:
  - zřetězení $u.v$ nebo $uv$
  - mocnina $u^n$, kde $n$ je počet opakování
  - délka slova $|u|$
  - počet výskytů $s \in \Sigma$ ve slově $u$ značíme $|u|_s$

Mezi jazyky můžeme dělat různé operace jako sjednocení, průnik, rozdíl a doplněk, funguje to jako operace množin, takže zbytečné definovat.

Další operace s jazyky:
- pozitivní iterace $L^+$
- obecná iterace $L^*$
- otočení jazyka $L^R$
- levý kvocient $L$ podle $M$, $M \setminus L = \{v|uv \in L \& u \in M\}$
- levá derivace $L$ podle $w$, $\partial_W L = \{ w \} \setminus L$

### Regulární jazyky

Regulární jazyky jsou ty jazyky, které jsou generovány regulární gramatikou a jsou rozpoznatelné $DFA, NFA$ nebo $\lambda-NFA$. Ty popíšeme později.

#### Regulární gramatiky

Gramatika je čtveřice $G = (V, T, P, S)$, kde:
1. $V$ je množina neterminálů (variables)
2. $T$ je množina terminálů (terminal symbols)
3. $S$ je počáteční symbol $S \in V$
4. $P$ je konečná množina pravidel (produkcí)

Pravidla mají tvar $\beta A \gamma \rightarrow \omega, A \in V, \beta, \gamma, \omega \in (V \cup T)^*$. Tedy levá strana vždy obsahuje alespoň jeden neterminální symbol.

Regulární gramatiky obsahují pouze pravidla tohoto typu: $A \rightarrow \omega B, A \rightarrow \omega, A, B \in V, \omega \in T^*$. Taková gramatika je pravá lineární. Levá lineární gramatika by byla, kdyby neterminál byl nalevo.

Levé a pravé lineární gramatiky zvlášť generují regulární jazyky, ale dohromady jsou již silnější, například jazyk $L = \{ 0^n 1^n | n \geq 1 \}$ není regulární, ale je generován lineární gramatikou ve tvaru $S \rightarrow 0S1|01$.

$\alpha$ se (přímo) přepíše na $\omega$, pokud existuje nějaké vhodné pravidlo, které přepsání splní. Posloupnost takových přepsání nazýváme derivací (odvozením). Z derivací lze postavit derivační strom.

Gramatika je víceznačná, pokud existuje aspoň jeden řetězec $w$ takový, že pro něj můžeme najít dva různé derivační stromy takové, že dávají $w$. Jinak je gramatika jednoznačná. 

Konečný automat lze vždy převést na gramatiku typu 3 a obráceně.

Dvě gramatiky jsou ekvivalentní právě tehdy, když generují stejný jazyk.

#### Deterministický a nedeterministický konečný automat

DFA $A = (Q, \Sigma, \delta, q_0, F)$ sestává z $Q$, což je konečná množina stavů, abecedy $\Sigma$, přechodové funkce $\delta: Q \times \Sigma \rightarrow Q$, počátečního stavu $q_0 \in Q$ a neprázdné množiny koncových (přijímajících) stavů $F \subseteq Q$.

Z definice lze nahlédnout, že pro každý stav a každý znak abecedy je jasné, že existuje právě jeden stav, do kterého se dostaneme.

Používá se také rozšířená přechodová funkce:
1. $\delta^*(q, \lambda) = q$
2. $\delta^*(q, wx) = \delta(\delta^*(q, w), x)$ pro $x \in \Sigma, w \in \Sigma^*$

Jazyk rozpoznávaný konečným automatem je takový jazyk, že všechna slova skončí v přijímajícím stavu. Třída jazyků rozpoznatelných konečnými automaty je nazvána regulární jazyky.

Iterační (pumping) lemma pro regulární jazyky: Mějme regulární jazyk $L$. Pak existuje konstanta $n \in \mathbb{N}$ (závislá na $L$) tak, že každé $w \in L, |w| \geq n$ můžeme rozdělit na tři části tak, že $w = xyz$ a platí:
1. $y \not = \lambda$
2. $|xy| \leq n$
3. $\forall k \in \mathbb{N}_0:$ slovo $xy^kz \in L$

Příklad použití pumping lemmatu: Jazyk slov se stejným počtem 0 a 1 není regulární. Předpokládejme, že regulární je. Vezměme $n$ z pumping lemmatu. Zvolme $w = 0^n 1^n \in L$. Pak $|xy| \leq n$, jenže obsahuje samé nuly. Pak by nešlo pumpovat nuly, porušila by se rovnost.

Mějme konečnou abecedu $\Sigma$ a relaci ekvivalence $~$ na $\Sigma^*$. Pak:
1. $~$ je pravá kongruence, jestliže $\forall u, v, w \in \Sigma^*: u ~ v \implies uw ~ vw$
2. je konečného indexu, má-li rozklad $\Sigma^* / ~$ konečný počet tříd
3. třídu kongruence $~$ obsahující slovo $u$ značíme $[u]_~$

Myhill–Nerodova věta: $L$ je rozpoznatelný konečným automatem právě tehdy, když existuje pravá kongruence konečného indexu nad $\Sigma^*$ tak, že $L$ je sjednocením jistých tříd rozkladu $\Sigma^* / ~$.

Řekněme, že v automatu je stav dosažitelný, jestliže existuje slovo takové, že po přečtení nějakého slova skončíme v daném stavu.

Dva automaty nad stejnou abecedou jsou ekvivalentní, jestliže rozpoznávají stejný jazyk. Dva stavy v automatu jsou ekvivalentní, pokud pro všechna slova z jazyku platí, že $\forall w; \delta^* (p,w) \in F \iff \delta^* (q,w) \in F$.

DFA je redukovaný, pokud nemá nedosažitelné stavy a žádné dva stavy nejsou ekvivalentní. Redukce je jednoduchá, stačí nalézt ekvivalentní stavy a poté je spojit v jeden stav.

Nedeterministický konečný automat (NFA) $A = (Q, \Sigma, \delta, S_0, F)$, kde se změnila pouze přechodová funkce $\delta: Q \times \Sigma \rightarrow \mathcal{P}(Q)$ vracející podmnožinu $Q$ a namísto počátečního stavu můžeme mít více počátečních stavů $S_0 \subseteq Q$.

Tedy vlastně se simuluje průběh ve více stavech najednou.

Dá se NFA rozšířit o $\lambda$ přechody, pak ho nazývejme $\lambda$-NFA. To se můžeme libovolně rozhodnout, jestli už přejdeme do dalšího stavu či ne.

Všechny $\lambda$-NFA i NFA se dají převést na DFA.

#### Regulární výrazy

Regulární výrazy $\alpha, \beta \in RegE(\Sigma)$ nad konečnou neprázdnou abecedou $\Sigma = \{ x_1, x_2, ..., x_n \}$ a jejich hodnota $L(\alpha)$ jsou definovány induktivně:
1. $L(\lambda) = \{ \lambda \}$
2. $L(\emptyset) = \{ \} = \emptyset$
3. $L(a) = \{ a \}$

Indukce je poté:
1. $L(\alpha + \beta) = L(\alpha) \cup L(\beta)$
2. $L(\alpha \beta) = L(\alpha) L(\beta)$
3. $L(\alpha^*) = L(\alpha)^*$
4. $L((\alpha)) = L(\alpha)$

Každý jazyk reprezentovaný konečným automatem lze zapsat jako regulární
výraz. Každý jazyk popsaný regulárním výrazem můžeme zapsat jako $\lambda$-NFA (a tedy i DFA).

Regulární jazyky jssou uzavřeny na všechny operace, tedy sjednocení, průnik, doplněk, homomorfismus, inverzní homomorfismus.

Poznámka: homomorfismus je zjednodušeně řečeno přeznačení abecedy.

### Bezkontextové jazyky

#### Bezkontextové gramatiky, jazyk generovaný gramatikou

Bezkontextová gramatika je gramatika, kde všechna pravidla jsou ve tvaru $A \rightarrow \omega, \omega \in (V \cup T)^*$.

Chomského normální forma (ChNF): Všechna pravidla jsou ve tvaru $A \rightarrow BC, A \rightarrow a$, kde $A, B, C \in V, a \in T$. Do tvaru Chomského normální formy se dají převést všechny bezkontextové gramatiky postupně eliminací zbytečných symbolů, eliminací $\lambda$ pravidel a jednotkových pravidel.

Důležité je pumping lemma pro bezkontextové jazyky: Mějme bezkontextový jazyk $L$. Pak existuje $n \in \mathbb{N}$ takové, že každé slovo $z \in L, |z| > n$ lze rozložit na $z = uvwxy$ tak, že:
1. $|vwx| \leq n$
2. $vx \not = \lambda$
3. $\forall i \geq 0, uv^iwx^iy \in L$

Příklad použití: Jazyk $L = \{ 0^n 1^n 2^n | n \geq 1 \}$ není bezkontextový. Předpokládáme, že bezkontextový je. Z lemmatu vezmeme číslo $n$, zvolíme $|0^n 1^n 2^n| > n$. Pumpovací slovo je $|vwx| \leq n$. Vždy tedy lze pumpovat 2 různé symboly, tím by se porušila rovnost počtu symbolů, tedy nemůže jazyk být bezkontextový.

Existuje algoritmus, který ověří, že slovo je generované CFL, tomu se říká Cocke-Younger-Kasami algorithm.

#### Zásobníkový automat, třída jazyků přijímaných zásobníkovými automaty

Zásobníkové automaty jsou rozšířením $\lambda$-NFA automatů s $\lambda$ přechody. Přidanou věcí je zásobník. Ze zásobníku můžeme číst, přidávat na vrch a odebírat z vrchu zásobníku. Zásobník je neomezeně velký a má vlastní abecedu. Deterministické zásobníkové automaty přijímají jen vlastní podmnožinu bezkontextových jazyků.

Zásobníkový automat (PDA) je $P = (Q, \Sigma, \Gamma, \delta, q_0, Z_0, F)$, kde:
1. $Q$ je konečná množina stavů
2. $\Sigma$ je neprázdná konečná množina vstupních symbolů
3. $\Gamma$ je neprázdná konečná zásobníková abeceda
4. $\delta$ je přechodová funkce $\delta: Q \times (\Sigma \cup \{ \lambda \}) \times \Gamma \rightarrow P({}_{FIN}(Q \times \Gamma^*))$. Navíc platí, že $\delta(p, a, X) \ni (q, \gamma)$, kde $q$ je nový stav, $\gamma$ je řetezec zásobníkových symbolů, který nahradí $X$ na vrcholu zásobníku
5. $q_0 \in Q$ je počáteční stav
6. $Z_0 \in \Gamma$ je počáteční zásobníkový symbol
7. $F$ je množina přijímajících stavů, může být nedefinovaná

Situace zásobníkového automatu je trojice $(q, w, \gamma)$, kde $q$ je stav, $w$ je zbývající vstup a $\gamma$ je obsah zásobníku. Situace značíme jako ID. Situace mohou tvořit posloupnosti.

Zásobníkový automat může přijímat dvěma způsoby: Buď prázdným zásobníkem, tedy po odebrání všech symbolů ze zásobníku některého ze stavů, nebo koncovým stavem (stejně jako u DFA). Síla těchto dvou druhů automatů je stejná.

Zásobníkové automaty přijímají stejné jazyky jako jsou ty generované bezkontextovou gramatikou.

Deterministický zásobníkový automat (DPDA) definujeme jako PDA, akorát pro každý stav máme nejvýše jednu kombinaci, tedy $\delta(q, a, X)$ je nejvýše jednoprvková $\forall(q, a, X) \in Q \times (\Sigma \cup \{ \lambda \}) \times \Gamma$ a je-li $\delta(q, a, X)$ neprázdná pro nějaké $a \in \Sigma$, pak $\delta(q, \lambda, X)$ musí být prázdná.

Pozor na to, že deterministické zásobníkové automaty jsou slabší, než nedeterministické. Dokážou však třeba přijmout jazyk $L = \{ wcw^R | w \in (0+1)^* \}$.

Bezkontextové jazyky jsou uzavřené na sjednocení, průnik s RL, homomorfismus a inverzní homomorfismus. Pozor, že nejsou uzavřené na průnik a doplněk.

Deterministické CFL jsou uzavřené na průnik s RL a doplněk s inverzním homomorfismem. Nejsou však uzavřené na sjednocení, průnik ani homomorfismus.

### Rekurzivně spočetné jazyky

#### Gramatika typu 0

Gramatiky typu 0 jsou v obecné formě $\alpha \rightarrow \beta, \alpha, \beta \in (V \cup T)^*, \alpha$ obsahuje neterminál. Tedy je to ta nejobecnější forma.

#### Turingův stroj

Turingův stroj (TM) je sedmice $M = (Q, \Sigma, \Gamma, \delta, q_0, B, F)$ se složkami:
1. $Q$ je konečná množina stavů
2. $\Sigma$ je konečná neprázdná množina vstupních symbolů
3. $\Gamma$ je konečná množina všech symbolů pro pásku
4. $\delta$ je přechodová funkce $(Q - F) \times \Gamma \rightarrow Q \times \Gamma \times \{ L, R \}$, platí $\delta(q, x) = (p, Y, D)$, kde $q \in (Q - F)$ je aktuální stav, $X \in \Gamma$ je aktuální symbol na pásce, $p$ je nový stav $p \in Q$, $Y \in \Gamma$ symbol pro zapsání do aktuální buňky, $F \subseteq Q$ množina koncových (přijímacích) stavů
5. $q_0 \in Q$ je počáteční stav
6. $B \in \Gamma - \Sigma$ je symbol pro prázdné buňky
7. $F \subseteq Q$ množina koncových stavů

TM zastaví, pokud vstoupí do stavu $q$ s čteným symbolem $X$ a $\delta(q, X)$ není definováno. Předpokládáme, že v přijímacím stavu $q \in F$ TM zastaví, dokud nezastaví, tak nevíme, jestli přijme či nepřijme slovo.

TM rozhoduje jazyk $L$, pokud $L = L(M)$ a pro každé $w \in \Sigma^*$ stroj nad $w$ zastaví. Jazyky rozhodnutelné TM nazýváme rekurzivní.

Každý rekurzivně spočetný jazyk je typu 0.

TM můžeme rozšířit tak, že přidáme více pásek, případně tak, že přidáme nedeterminismus. Obě taková rozšíření však mají stejnou sílu jako původní TM.

#### Algoritmicky nerozhodnutelné problémy

Chceme dojít k důkazu nerozhodnutelnosti jazyka dvojic $(M, w)$ takových, že:
1. $M$ je binárně kódovaný Turingův stroj s abecedou \{ 0, 1 \}
2. $w \in \{ 0, 1 \}^*$
3. $M$ nepřijímá vstup $w$

Diagonální jazyk $L_d = \{ w, $ TM reprezentovaný jako $w$ takový, že nepřijímá $ w \}$

Neexistuje TM přijímající jazyk L_d, protože by to vedlo k paradoxu.

Definujeme univerzální jazyk $L_u$ jakožto množinu binárních řetězců, které kódují pár $(M, w)$, kde $M$ je TM a $w \in L(M)$. TM rozpoznávající $L_u$ se nazývá Univerzální Turingův stroj.

Problémem $P$ myslíme matematicky/informaticky definovanou množinu otázek
kódovatelnou řetězci nad abecedou $\Sigma$ s odpověďmi $\in \{ano, ne\}$.

Problém je (algoritmicky) rozhodnutelný, pokud existuje Turingův stroj TM
takový, že pro každý vstup $w \in P$ zastaví a navíc přijme právě když $P(w) = ano$
(tj. pro $P(w) = ne$ zastaví v ne–přijímacím stavu).

Problém, který není algoritmicky rozhodnutelný nazýváme nerozhodnutelný
problém.

$L_u$ je rekurzivně spočetný, ale není rekurzivní.

Instance Postova korespondenčního problému (PCP) jsou dva seznamy slov nad abecedou $\Sigma$ značené $A = w_1,w_2, ... ,w_k$ a $B = x_1, x_2, ... , x_k$ stejné délky $k$. Pro každé $i$, dvojice $(w_i, x_i)$ se nazývá odpovídající dvojice.
Instance PCP má řešení, pokud existuje posloupnost jednoho či více přirozených čísel $i_1, i_2, ..., i_m$ tak, že $w_{i_1}w_{i_2} ... w_{i_m} = x_{i_1} x_{i_2} ... x_{i_m}$ tj. dostaneme stejné slovo. V tom případě říkáme, že posloupnost $i_1, i_2, ..., i_m$ je řešení. Postův korespondenční problém je: Pro danou instanci PCP, rozhodněte, zda
má řešení.

Je algoritmicky nerozhodnutelné, zda je bezkontextová gramatika víceznačná.

### Chomského hierarchie

Gramatikám typu 0 odpovídají rekurzivně spočetné jazyky, jsou rozpoznatelné Turingovými stroji.

Gramatikám typu 1 odpovídají kontextové gramatiky, jsou rozpoznatelné lineárně omezenými automaty.

Obsahují pouze pravidla typu $\alpha A \beta \rightarrow \alpha \omega \beta, A \in V, \alpha, \beta \in (V \cup T)^*, \omega \in (V \cup T)^+$ s výjimkou pravidla $S \rightarrow \lambda$, ovšem pak se $S$ neobjevuje nikde jinde.

Příklad kontextového jazyka: $L = \{ a^n b^n c^n | n \geq 1 \}$.

Gramatikám typu 2 odpovídají bezkontextové jazyky, jsou rozpoznávany nějakým PDA.

Gramatikám typu 3 odpovídají regulární/pravé lineární jazyky, jsou rozpoznávány DFA/NFA/$\lambda$-NFA.

#### Schopnost zařazení konkrétního jazyka do Chomského hierarchie (zpravidla sestrojení odpovídajícího automatu či gramatiky)

Tohle bych řekl, že je spíš o trénování, pro regulární jazyky je celkem jednoduché vymyslet nějaký DFA/NFA, pro bezkontextové a výše je lepší vymyslet nějakou gramatiku.
