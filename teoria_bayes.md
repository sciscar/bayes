# Probabilitat
## Probabilitat condicionada
## Teorema de Bayes
## Inferència Bayesiana

La teoria de la probabilitat està relacionada amb fenòmens en els quals es compleix la condició d'atzar; això és, aquells en els quals resulta impossible predir els seus resultats. En aquesta teoria, cadascun dels resultats que produeix un d'aquests fenòmens (o experiments) rep el nom de resultat. Per exemple, un d'aquests experiments és el llançament de monedes amb els resultats cara i creu, o llançar un dau de 6 cares, amb un resultat d'entre {1, 2, 3, 4, 5, 6}.

El conjunt de tots els resultats possibles d'un experiment aleatori rep el nom d'espai mostral i cadascun dels elements del conjunt (és a dir, cada resultat) rep el nom de succés elemental. Així, l'espai mostral del llançament d'una moneda pot representar-se mitjançant el conjunt O={c,x} i el del llançament de dues monedes seria el conjunt O={(c,c),(c,x),(x,c),(x,x)} on el primer element de cada parell ordenat representa el resultat de la primera moneda i el segon element indica el cas obtingut en la segona moneda.

En espais mostrals finits, un succés d'un experiment aleatori és tot subconjunt de l'espai mostral associat a aquest experiment. Per exemple, per al llançament d'un dau, amb espai mostral O={1,2,3,4,5,6}, el succés que en llançar el dau isca un nombre parell ve donat pel conjunt A={2,4,6}, o el succés que isca un número múltiple de tres és el conjunt B={3,6}.

Hi ha dos casos particulars de successos que sempre existeixen en tot espai mostral: El succés format per tots els resultats possibles, A=O, i rep el nom de succés segur; i el format per resultats que no es poden reasseure mai, A=∅, que rep el nom de succés impossible.

Es diu que P és una funció de probabilitat, o simplement una probabilitat, sobre l'espai mostral O, si P és una aplicació sobre successos que pren valors en l'interval [0,1], verificant els següents axiomes:

1. Es considera que la màxima probabilitat s'estableix a 1 i aquest valor s'ha d'establir solament quan se sap que el succés és totalment cert. Com sempre és cert que ocorrerà un resultat de l'espai mostral, la probabilitat del succés segur necessàriament ha de ser 1.
2. Per a qualsevol succés A, P(A)≥0. Una interpretació intuïtiva d'aquest axioma és la següent. Per l'Axioma 1, la màxima massa de probabilitat (que és 1) es distribueix sobre tot l'espai mostral O. Com un succés, posem A, és qualsevol regió de l'espai mostral, s'estableix la seua massa de probabilitat proporcional a l'àrea que ocupa. Com qualsevol regió té una àrea no negativa, la seua probabilitat haurà de ser positiva o nul·la (si la regió està buida).
3. Per a qualsevol dos successos A i B mútuament excloents o incompatibles (matemàticament A∩B=∅), llavors P(A∪B)=P(A)+P(B). A aquest axioma se'l coneix per la propietat d'aditividad i el que estableix és com calcular la probabilitat de dos successos que no comparteixen elements mostrals (o que produeixen resultats diferents).

Al parell (O,P) se'n diu espai probabilístic i se sol dir que P és una funció de probabilitat sobre O.

Alguns resultats immediats que poden deduir-se de l'axiomàtica anterior són els següents:

- P(∅)=0
- P(O−A)=1−P(A)
- Per a qualsevol successió finita de successos mútuament excloents o incompatibles (matemàticament A1,A2,...,An; A i ∩A j =∅), llavors P(⋃ i=1 n Ai)=∑ i=1 n P(Ai)

Donades dos variables X i I, es defineix la probabilitat condicionada de X, donat un valor concret de I, com el conjunt de valors donats per l'expressió:

$$
P(X∣I)=P(X=x∣I=i)= P(i) / P(x,i) sempre que P(i) ≠ 0.
$$ 

En el cas que P(i) = 0, llavors la probabilitat condicionada està sense definir. Tingues en compte que en una expressió P(X∣i), i és un valor fix d'I i X és un valor que es mou en tot el seu domini.

El concepte de dependència està relacionat amb el de correlació: indica que la presència d'i afavoreix la presència del valor x i es parla de correlació positiva entre tots dos valors; si la presència d'i desfavoreix la presència de x, P(x∣i) < P(x), es parla llavors de correlació negativa.

Un exemple de correlació positiva és la relació entre les variables preu i pes d'un producte: com més pague, més quilos del producte tindrà i com menys quilos adquirisca menys haurà de pagar. La relació entre l'edat i la capacitat de memòria a curt termini està, per contra, correlada negativament: com més vells ens fem més probable és que oblidem el que vam fer el dia anterior.

Un altre resultat que també és important és el següent:
Si ∑ i=1 n P(xi) = 1 amb ∀ x, P(xi ∪xj) = P(xi) + P(xj), llavors P(i) = ∑ i=1 n P(i∣xi)∗P(xi).

En aquest apartat es mostren els resultats més importants del càlcul de probabilitats i que constitueixen la base dels motors d'inferència dels sistemes intel·ligents probabilístics. El més important és el teorema de Bayes que, en la seua versió més simple, estableix que:

$$
P(X∣i) = P(i∣X)P(X) / P(i)
$$

També d'aquesta manera:
$$
P(X∣i) = ∑ i=1 n P(i∣xi)∗P(xi) / ∑ i=1 n P(xi) = 1.
$$

Es pot interpretar com segueix. El nostre model parteix d'una probabilitat a priori sobre la credibilitat dels valors de X. Llavors, en algun instant, observem que una altra variable I s'instancia al valor i. Ja sap que com de probable és un valor de X quan I s'ha instanciat al valor i ve donat per la probabilitat (condicionada) P(X∣i). Tu ja saps com obtenir-la a partir de P(xi,i) però com obtenir-la a partir d'aquella probabilitat inicial P(X)? La regla de Bayes ens dona la solució i pot entendre's com una fórmula per a passar de la probabilitat a priori, P(X), a una probabilitat a posteriori, P(X∣i). És a dir, el teorema de Bayes descriu com canvia la probabilitat quan aprenem nova informació.

Un exemple clàssic és el camp mèdic on X representa una malaltia que pot manifestar-se mitjançant una sèrie símptomes I. El metge davant la presència positiva o negativa d'aquests símptomes estableix un diagnòstic sobre la presència de la malaltia X. El diagnòstic no se sol establir en termes de total certitud, sinó que estaria sotmès a un cert risc subjectiu del propi metge però que, matemàticament, es pot determinar mitjançant el teorema de Bayes.

La probabilitat P(i∣x) és coneguda com a versemblança. Més concretament, és la versemblança o creença de i donada per x. Tingues en compte que i és és un valor fix i que x pren valors en el seu domini, per la qual cosa no s'interpreta com una probabilitat condicionada. És per això que alguns autors prefereixen denotar aquesta funció per L(x∣i).

Exemple d'Inferència Bayesiana: L'embaràs de Bayes

Una vesprada qualsevol, una dona sospita que pot estar embarassada. Per a estar segura del seu estat compra un test del qual es coneix que té una eficàcia del 90% a detectar embarassos. Com queda dit, el test té una eficàcia del 90% a detectar embarassos; afegir que dona falsos positius el 50% de les vegades. La probabilitat de quedar-se embarassada després de mantenir una relació sexual sense protecció és del 15%.

També podem crear una matriu de confusió per a l'operativa del test:

|             | Embaràs (+) | No embaràs (-) |
|-------------|-------------|---------------|
| Test +      |    0.90     |     0.50      |
| Test -      |    0.10     |     0.50      |

Amb 0.56 sent P(+) i 0.44 el seu complementari P(-).

El contingut d'aquesta taula són les probabilitats condicionades d'una evidència (+ o -) enfront d'una hipòtesi (embaràs o no embaràs). La dona es realitza el test i obté un resultat positiu. Pregunta: Quina és la probabilitat que aquesta dona estigui embarassada?

Atès que sabem la probabilitat d'estar embarassada (15%) i la de no estar-ho (85%) podem calcular P(+) a partir de la matriu de confusió. Partim d'una hipòtesi H0 amb una probabilitat P(H0) = 0.15 atès que la dona creu que té alguna oportunitat d'estar embarassada.

Primer test:
Després de fer-se el test d'embaràs, aquest llança un resultat positiu (+). Per tant:

$$
P(H0∣t1=+) = P(t1) * P(t1∣H0) / P(t1)
$$

$$
P(t1=+) = P(+∣H0) * P(H0) + P(+∣¬H0) * P(¬H0) = 0.56
$$

No quedant contenta, torna a realitzar el test d'embaràs.

Segon test:
Una vegada fet aquest, de nou llança un resultat positiu (+). Però abans hem d'actualitzar P(H1).

La probabilitat de la nova hipòtesi és P(H1) = P(H0∣t1), que és la hipòtesi inicial tenint en compte l'anterior evidència. Per tant:

$$
P(H1∣t2=+) = P(t2) * P(t2∣H1) / P(t2)
$$

$$
P(t2=+) = 0.90 * 0.241 + 0.50 * (1−0.241) = 0.5964
$$

Tercer test:
Una vegada fet aquest, de nou llança un resultat positiu (+). I hem d'actualitzar P(H2):

$$
P(t3=+) = 0.90 * 0.364 + 0.50 * (1−0.364) = 0.6456
$$

La probabilitat de la nova hipòtesi és P(H2) = P(H1∣t2), que és la hipòtesi inicial tenint en compte l'anterior evidència. Per tant:

$$
P(H2∣t3=+) = P(t3) * P(t3∣H2) / P(t3)
$$
Així que va ser després de tres intents quan la probabilitat d'estar embarassada, havent produït tres positius seguits, ha superat el 50%.

Codi en Python per calcular probabilitats condicionades

```python

# Calculant P(+) a partir de la matriu de confusió
# li passem la probabilitat d'estar embarassada (e) i la de no estar-ho (*ne)
# si no li passem '*ne', deduïm que és '1-e'
def pplus(e: float, ne: float = None):
    assert e >= 0.0 and e <= 1.0
    assert ne == None or (ne >= 0.0 and ne <= 1.0)
    return e * 0.90 + ((1 - e) if ne == None else ne) * 0.50

# Partim de la hipòtesi que estem embarassats.
Pemb = 0.15
Pnemb = 0.85
PH = [Pemb]
PtH = 0.90
PHt = (PtH * PH[-1]) / pplus(Pemb, Pnemb)
print("Primer intent", PHt, f"({round(PHt * 100, 2)}%)")
PH.append(PHt)

```

Resultat del primer intent:
```
Primer intent 0.24107142857142858 (24.11%)

```

Fem una segona prova, amb resultat positiu:

```python
# Ara no partim de la hipòtesi inicial, si no de l'anterior
Pemb = PH[-1]
Pnemb = 1 - PHt
PHt = (PtH * PH[-1]) / pplus(Pemb, Pnemb)
print("Segon intent", PHt, f"({round(PHt * 100, 2)}%)")
PH.append(PHt)
```

Resultat del segon intent:
```python

Segon intent 0.36458333333333337 (36.46%)

```

Fem una tercera prova, amb resultat positiu:

```python
# Ara no partim de la hipòtesi inicial, si no de l'anterior
Pemb = PH[-1]
Pnemb = 1 - PHt
PHt = (PtH * PH[-1]) / pplus(Pemb, Pnemb)
print("Tercer intent", PHt, f"({round(PHt * 100, 2)}%)")
PH.append(PHt)
```

Resultat del tercer intent:
```python
Tercer intent 0.5071892393320966 (50.72%)
```

