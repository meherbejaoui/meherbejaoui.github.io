---
title: "Les bases de Python"
excerpt: "Les bases du langage Python"
categories: python
header:
  teaser: /assets/images/python-powered.jpg
author_profile: false
classes: wide
tags:
- tutorial
- python
---
***
## Sommaire

- [Introduction à Python](#utiliser-python-comme-une-calculatrice)
- [Contrôle du flux](#contrôle-du-flux)
- [Structures de données](#structures-de-données)
- [Modules](#modules)

***
### Utiliser Python comme une calculatrice
Après avoir [installé Python](https://docs.python.org/3/using/windows.html#installing-python), vous pouvez ouvrir une *console* ou *l'invite de commande*, tapez python et un intepréteur Python s'ouvre.
Pour l'instant, nous utilisons ce [notebook](/assets/IntroductionPython.ipynb).  
Essayons quelques commandes Python simples


```python
2+3 # Un commentaire
```




```python
20 + 11 * 3
```




```python
(20 - 11) / 4
```

Les nombres entiers (comme 2, 3 et 11) sont de type **`int`**, alors que les décimaux (comme 10.0 et 3.14) sont de type **`float`**.


```python
19 / 3 # La division (/) donne toujours un nombre de type 'float'
```




```python
19 // 3 # L'opérateur (//) effectue des divisions entières
```




```python
19 % 3  # L'opérateur (%) donne le reste de la division entière.
```

Il est possible de calculer des puissances (X<sup> y</sup>) avec l’opérateur `**`


```python
3 ** 2
# 11 ** 12. # les opérations avec des types d'opérandes mélangés donnent un résultat en virgule flottante
```

Le signe égal ( `=` ) permet d'affecter une valeur à une variable


```python
hauteur = 7
base = 9
aire_du_triangle = (hauteur * base) / 2
aire_du_triangl    # parlons des erreurs dans l'affichage des résultats
```

***
### Les chaînes de caractères
Les chaînes de caractères peuvent être exprimés de différentes manières :


```python
'Bonjour' # guillemets simples
"Hello" # guillemets doubles
```




```python
'de l\'art' # utiliser \' pour protéger les guillemets
# "de l'art" # ou utiliser les guillemets doubles
```




```python
'"Le petit chat est mort. ", dit Agnès'
# "\"Le petit chat est mort. \", dit Agnès"
```

La fonction **`print()`** affiche les chaînes de caractères de manière plus lisible.


```python
'"L\'art !" dit Michel.'
# print ('"L\'art !" dit Michel.')
# p = 'Première ligne.\nDeuxième ligne.' # \n signifie nouvelle ligne
# p
# print (p)
```

Utilisez les chaînes brutes (`raw strings`) en préfixant la chaîne d’un **`r`**, pour éviter que les caractères précédés d’un antislash ne soient interprétés comme étant spéciaux.


```python
print('C:\Documents\nom')
# print(r'C:\Documents\nom') # les guillemets précédés par (r)
```

Utilisez des triples guillemets : `'''abc'''` ou `"""xyz"""` pour écrire des chaînes de caractères qui s'étalent sur plusieurs lignes.  

Empêcher le retour à la ligne en ajoutant **`\`**


```python
print("""\
Définitions:
     -dictionnaire           Une structure de donnée associant des clefs et des valeurs
     -fonction               Une suite d’instructions qui renvoient une valeur à celui qui l’appelle
""")
```

L’opérateur **`+`** permet de coller (concaténer) plusieurs chaînes. L'opérateur **`*`** permet de répéter les chaînes.


```python
'OUI ' * 3 + 'Hurrah!'
# prefix = 'Hello Wo'
# prefix + 'rld!'
```

Les caractères peuvent être accédés par leur position. Pour l'indexation des chaînes de caractères, le premier caractère est à la position **0**.


```python
phrase = "Je m'appelle Brian"
phrase[0]
# phrase[15]
```

Pour effectuer un décompte en partant de la droite, nous utilisons des indices négatifs (commencent par **-1**).


```python
phrase[-1]
# phrase[-3]
# phrase[-18]
```

Pour obtenir une sous-chaîne :


```python
phrase[0:2] # caractères de la position 0 (inclut) à 2 (exclu)
# phrase[13:18]
# phrase[:12]
# phrase[12:] # s[:i] + s[i:] = s
# phrase[-5:]
# phrase[20] # indice trop grand (hors bornes)
# phrase[5:20] # gérés silencieusement si utilisés dans des tranches
```

Les chaînes de caractères sont `immutable` : elles ne peuvent pas être modifiées.


```python
phrase = "Je m'appelle Brian"
phrase[1] = 'j'
# phrase[13:] = 'Stewie'
# phrase[:13] + 'Stewie !'
```

La fonction **`len()`** donne la longueur d'une chaîne :


```python
p = 'I have a dream'
len(p)
```

***
### Les listes
Une suite d'éléments séparés par des virgules, placés entre crochets. Les éléments d’une liste ne sont pas obligatoirement du même type.


```python
premiers  = [2, 3, 5, 7, 11]
premiers
```

Les listes peuvent être indicées et découpées :


```python
premiers[0]
# premiers[-1]
# premiers[2:10]
```

Les opérations de découpage (en tranches) renvoient une nouvelle liste contenant les éléments spécifiés.


```python
premiers[:] # une copie de la liste
```

Les listes supportent des opérations comme pour les chaînes de caratcères.


```python
premiers + [13, 17, 19]
# premiers * 2
```

Il est possible de changer le contenu des listes : elles sont `mutables`


```python
nbres = [1, 2, 'c', 4]
# nbres[2] = 3
nbres
```




```python
nbres.append(5) # méthode pour ajouter des éléments à la fin
nbres
```




```python
nbres[2:4] = [10, 100] # affectation par tranches
# nbres[:] = [] # supprimer toutes les valeurs
nbres
```

Il est possible de créer des listes contenant d'autres listes :


```python
a = [1, 2, 3]
b = ['f', 'r', 'a']
res = [a, b]
# res
# res[1]
# res[0][2]
```

La compréhension des listes (`list comprehension`) permet de construire des nouvelles listes où chaque élément est le résultat d'une opération appliquée à chaque élément d’une autre séquence; ou de créer une sous-séquence d'éléments satisfaisants une certaine condition.  
Elle consiste en deux crochets contenants une expression suivie par une clause **`for`**, puis par une ou plusieurs clauses **`for`** ou **`if`**.


```python
[x for x in range(6) if x % 2 == 0]
```




```python
[(x, y) for x in [1,2,3] for y in [3,1] if x != y]
```

***
### Contrôle du flux
#### L’instruction `if` :


```python
x = 11
if x % 2 == 0:
    print ('foo')
    s = 'nombre pair'
else:    
    print ('bar')    # x % 2 != 0
```




```python
x = 20
if x % 5 == 0 and x % 2 == 0:
    print ('foobar')
elif x % 5 == 0:
    print ('foo')
else:
    print ('bar')
```

#### L'instruction `for` :
Elle permet d'itérer sur les éléments d'une séquence (une liste, une chaîne de caractères, etc.) par ordre.


```python
pays = ['France', 'Canada', 'Belgique', 'Suisse']
for p in pays:
    print (p, len(p))
```




```python
mot = '1 chat'
for c in mot:
    print (c)
```




```python
for i in range(1, 4):
    print (i ** 2)
```

#### L'instruction `while` :


```python
x = 1
while x <= 5:
    print (x, end=' ') # Le paramètre (end) sert à enlever le retour à la ligne, ou terminer par un autre caractère
    x += 2 # x = x + 2
```

##### Les fonctions :
Le mot-clé **`def`** définit la fonction. Il est suivi du nom de la fonction, et de ses paramètres entre parenthèses.


```python
def add(n):         # calculer la somme des chiffres de 1 à n
    somme = 0       # une variable locale
    for i in range(1, n+1):
        somme += i
    return somme
add(3)
# add(10)

# somme # n'est pas défini 'globalement'
# somme = 100        # variable globale
# somme
```




```python
def fib(a, b, n):
    """ print une suite de fibnoacci à partir des termes a et b, jusqu'à n """
    while a < n:
        print(a, end=' ')
        a, b = b, a+b
fib(5, 8, 2000) '''{même les fonctions sans instruction
                 return renvoient une valeur, quoique ennuyeuse. Cette valeur est appelée None }'''
```

***
### Structures de données
#### Tuples
Une séquence d'éléments séparés par des virgules (et encadrés par des parenthèses si nécessaire)


```python
t = 'python', 3.5, 101
t
# t[2]

# n = t,  'Guido', ('2.7', 2010), [0, 90] # tuples imbriqués
# n
```




```python
n[1] = 'Guido van Rossum' # ils sont immutables
# n[3][1] = 100
n
```




```python
vide = () # initier un tuple vide
# un = 'python',
```

#### Les ensembles (`sets`)
Une collection non ordonnée, sans élément dupliqué.


```python
notes = {18, 15, 14, 11 ,18, 14}
notes
# fruits = {'orange', 'raisin', 'pomme' ,'kiwi' , 'orange', 'pomme'}
# fruits
```




```python
a = set('abccba')
a
# a & set('atta') # supportent d'autres opérations (unions, intersections, différences, etc.)
```

#### Dictionnaires
Des ensembles non ordonnés de pairs **`clé` : `valeur`** (`key` : `value` pairs). Ils sont indexés par des `clés` (keys), qui peuvent être de n’importe quel type immuable : chaînes de caractères, nombres et tuples (s’ils ne contiennent que des `immutables`).  
Les clés doivent être uniques au sein d'un dictionnaire.


```python
d = {} # créer un dictionnaire vide

# d = {'Marie':15, 'Jean':2, 'Victor':9}
# d['Marie']
# del d['Victor']
# d['Charles'] = 33
d
```




```python
p = dict([('Anthony', 'a'), ('Guido', [0, 'g']), ('Marie', 'm')])
# p.keys()
# p.values()
# 'guido' in p
# 'Guido' in p
```

Création des dictionnaires par compréhension (`dict comprehensions`).


```python
{x: x**3 for x in range(1, 6)}
```

***
### Modules
Un module est un fichier contenant des définitions et des instructions. Le nom du fichier est celui du module, suffixé de **`.py`**.
```python
import <module> # importer le module dans la table des symboles

<module>.<fonction> # accéder aux fonctions (ou constantes)
```   
Pour importer les noms d'un **`<module_1>`** directement dans la table des symboles du module qui l'importe (**`<module_2>`**). De ce fait, le nom du **`<module_1>`** n'est pas défini à l'intérieur du **`<module_2>`**
```python
from <module> import <fonction_1>, <fonction_2>, <fonction_n>
```
Ou bien
```python
from <module> import * # importer tous les noms du module (déconseillé)
```

***
## Exercice pratique de synthèse
- Définir une fonction `somme_impairs` qui prend une liste de nombres comme argument, et renvoie la somme de tous les entiers impairs. Par exemple :  
```python
somme_impairs([5, -13, 3]) = -5
somme_impairs([2, 1, 1.01) = 1
```
- Écrire un programme qui prend une valeur entrée par l'utilisateur (1 <= N <= 100), et affiche un message comme suit :  

```python
 - "Votre valeur X est plus grande. Essayer de nouveau !" # si la valeur entrée est plus grande à celle du programme
 - "Votre valeur X est plus petite. Essayer de nouveau !" # si la valeur entrée est plus petite à celle du programme
 - "Bravo ! C'était bien X"                               # si la valeur entrée est correcte
```  

Avec X est la valeur entrée par l'utilisateur.  
Penser à utiliser la fonction **`randint`** du module **`random`** pour générer un entier aléatoirement.  

```python
from random import randint
n = randint(1, 100)
```  

Pour plus de détails sur n'importe quel objet,  fonction ou module, utiliser : **`help(<nom>)`**
