# Guide de style Python de Google
![](https://img.shields.io/badge/contact-dr.mokira%40gmail.com-blueviolet)
![](https://img.shields.io/badge/lastest-2023--05--08-success)
![](https://img.shields.io/badge/status-en%20r%C3%A9daction%20-yellow)

<details>
  <summary>Table des Contenus</summary>

  <ul>
    <li><a href="#1-contexte">1 Contexte</a></li>
    <li><a href="#2-règle-du-langage-python">2 Règle du langage Python</a>
      <ul>
        <li><a href="#21-lint">2.1 Lint</a></li>
        <li><a href="#22-importations">2.2 Importations</a></li>
        <li><a href="#23-les-paquets">2.3 Les paquets</a></li>
        <li><a href="#24-les-exceptions">2.4 Les exceptions</a></li>
        <li><a href="#25-etat-global-mutable">2.5 État global mutable</a></li>
        <li><a href="#26-classes-et-fonctions-imbriquées-locales-intérieures">2.6 Classes et fonctions imbriquées/locales/intérieures</a></li>
        <li><a href="#27-comprehensions-expressions-de-generator">2.7 Comprehensions &amp; Expressions de Generator</a></li>
        <li><a href="#28-itérateurs-et-opérateurs-par-défaut">2.8 Itérateurs et opérateurs par défaut</a></li>
        <li><a href="#29-générateurs">2.9 Générateurs</a></li>
        <li><a href="#210-fonction-lambda">2.10 Fonction Lambda</a></li>
        <li><a href="#211-expressions-conditionnelles">2.11 Expressions conditionnelles</a></li>
        <!-- <li><a href="#212-default-argument-values">2.12 Default Argument Values</a></li> -->
        <!-- <li><a href="#213-properties">2.13 Properties</a></li> -->
        <!-- <li><a href="#214-truefalse-evaluations">2.14 True/False Evaluations</a></li> -->
        <!-- <li><a href="#216-lexical-scoping">2.16 Lexical Scoping</a></li> -->
        <!-- <li><a href="#217-function-and-method-decorators">2.17 Function and Method Decorators</a></li> -->
        <!-- <li><a href="#218-threading">2.18 Threading</a></li> -->
        <!-- <li><a href="#219-power-features">2.19 Power Features</a></li> -->
        <!-- <li><a href="#220-modern-python">2.20 Modern Python: from __future__ imports</a></li> -->
        <!-- <li><a href="#221-type-annotated-code">2.21 Type Annotated Code</a></li> -->
      </ul>
    </li>
    <!--<li><a href="#s3-python-style-rules">3 Python Style Rules</a>
      <ul>
        <li><a href="#s3.1-semicolons">3.1 Semicolons</a></li>
        <li><a href="#s3.2-line-length">3.2 Line length</a></li>
        <li><a href="#s3.3-parentheses">3.3 Parentheses</a></li>
        <li><a href="#s3.4-indentation">3.4 Indentation</a>
          <ul>
            <li><a href="#s3.4.1-trailing-commas">3.4.1 Trailing commas in sequences of items?</a></li>
          </ul>
        </li>
        <li><a href="#s3.5-blank-lines">3.5 Blank Lines</a></li>
        <li><a href="#s3.6-whitespace">3.6 Whitespace</a></li>
        <li><a href="#s3.7-shebang-line">3.7 Shebang Line</a></li>
        <li><a href="#s3.8-comments-and-docstrings">3.8 Comments and Docstrings</a>
          <ul>
            <li><a href="#s3.8.1-comments-in-doc-strings">3.8.1 Docstrings</a></li>
            <li><a href="#s3.8.2-comments-in-modules">3.8.2 Modules</a></li>
            <li><a href="#s3.8.2.1-test-modules">3.8.2.1 Test modules</a></li>
            <li><a href="#s3.8.3-functions-and-methods">3.8.3 Functions and Methods</a></li>
            <li><a href="#s3.8.4-comments-in-classes">3.8.4 Classes</a></li>
            <li><a href="#s3.8.5-block-and-inline-comments">3.8.5 Block and Inline Comments</a></li>
            <li><a href="#s3.8.6-punctuation-spelling-and-grammar">3.8.6 Punctuation, Spelling, and Grammar</a></li>
          </ul>
        </li>
        <li><a href="#s3.10-strings">3.10 Strings</a>
          <ul>
            <li><a href="#s3.10.1-logging">3.10.1 Logging</a></li>
            <li><a href="#s3.10.2-error-messages">3.10.2 Error Messages</a></li>
          </ul>
        </li>
        <li><a href="#s3.11-files-sockets-closeables">3.11 Files, Sockets, and similar Stateful Resources</a></li>
        <li><a href="#s3.12-todo-comments">3.12 TODO Comments</a></li>
        <li><a href="#s3.13-imports-formatting">3.13 Imports formatting</a></li>
        <li><a href="#s3.14-statements">3.14 Statements</a></li>
        <li><a href="#s3.15-accessors">3.15 Accessors</a></li>
        <li><a href="#s3.16-naming">3.16 Naming</a>
          <ul>
            <li><a href="#s3.16.1-names-to-avoid">3.16.1 Names to Avoid</a></li>
            <li><a href="#s3.16.2-naming-conventions">3.16.2 Naming Conventions</a></li>
            <li><a href="#s3.16.3-file-naming">3.16.3 File Naming</a></li>
            <li><a href="#s3.16.4-guidelines-derived-from-guidos-recommendations">3.16.4 Guidelines derived from Guido’s Recommendations</a></li>
          </ul>
        </li>
        <li><a href="#s3.17-main">3.17 Main</a></li>
        <li><a href="#s3.18-function-length">3.18 Function length</a></li>
        <li><a href="#s3.19-type-annotations">3.19 Type Annotations</a>
          <ul>
            <li><a href="#s3.19.1-general-rules">3.19.1 General Rules</a></li>
            <li><a href="#s3.19.2-line-breaking">3.19.2 Line Breaking</a></li>
            <li><a href="#s3.19.3-forward-declarations">3.19.3 Forward Declarations</a></li>
            <li><a href="#s3.19.4-default-values">3.19.4 Default Values</a></li>
            <li><a href="#s3.19.5-nonetype">3.19.5 NoneType</a></li>
            <li><a href="#s3.19.6-type-aliases">3.19.6 Type Aliases</a></li>
            <li><a href="#s3.19.7-ignoring-types">3.19.7 Ignoring Types</a></li>
            <li><a href="#s3.19.8-typing-variables">3.19.8 Typing Variables</a></li>
            <li><a href="#s3.19.9-tuples-vs-lists">3.19.9 Tuples vs Lists</a></li>
            <li><a href="#s3.19.10-typevars">3.19.10 Type variables</a></li>
            <li><a href="#s3.19.11-string-types">3.19.11 String types</a></li>
            <li><a href="#s3.19.12-imports-for-typing">3.19.12 Imports For Typing</a></li>
            <li><a href="#s3.19.13-conditional-imports">3.19.13 Conditional Imports</a></li>
            <li><a href="#s3.19.14-circular-dependencies">3.19.14 Circular Dependencies</a></li>
            <li><a href="#s3.19.15-generics">3.19.15 Generics</a></li>
            <li><a href="#s3.19.16-build-dependencies">3.19.16 Build Dependencies</a></li>
          </ul>
        </li>
      </ul>
    </li>
    <li><a href="#4-parting-words">4 Parting Words</a></li> -->
  </ul>

</details>

<!-- > Dans ce cour et tous les autres cours à venir, si le symbole `~$` se trouve
> au début d'un block de code, cela signifie qu'il s'agit de lignes de commande
> qu'on peut exécuter dans un terminal.-->

## 1 Contexte
Python est le principal langage dynamique utilisé chez Google. Ce guide de
style est une liste de choses à faire et à ne pas faire pour les programmes
Python.<br/>
Pour vous aider à formater le code correctement, nous avons créé un fichier de
[configuration pour Vim](https://google.github.io/styleguide/google_python_style.vim).
Pour Emacs, les paramètres par défaut devraient convenir.<br/>
De nombreuses équipes utilisent l'auto-formateur de
[Black](https://github.com/psf/black) ou
[Pyink](https://github.com/google/pyink) pour éviter de se disputer
sur le formatage.

## 2 Règle du langage Python
### 2.1 Lint
Exécutez `pylint` sur votre code en utilisant ce
[pylintrc](https://google.github.io/styleguide/pylintrc).

#### 2.1.1 Définition
`pylint` est un outil permettant de trouver des bugs et des problèmes de style
dans le code source Python. Il trouve des problèmes qui sont typiquement
détectés par un compilateur pour des langages moins dynamiques comme C et C++.
En raison de la nature dynamique de Python, certains avertissements peuvent
être incorrects; cependant, les avertissements erronés devraient être assez
rares.

#### 2.1.2 Avantage
Il détecte les erreurs faciles à éviter, comme les fautes de frappe,
l'utilisation de variables avant l'affectation, etc.

#### 2.1.3 Conséquence
`pylint` n'est pas parfait. Pour en tirer parti, nous devrons parfois écrire
autour de lui, supprimer ses avertissements ou le corriger.

#### 2.1.4 Décision
Assurez-vous d'exécuter `pylint` sur votre code.
Supprimez les avertissements s'ils sont inappropriés afin que d'autres
problèmes ne soient pas cachés. Pour supprimer les avertissements, vous pouvez
définir un commentaire au niveau de la ligne:

###### `</> PYTHON [01]`
```python
def do_PUT(self):  # WSGI name, so pylint: disable=invalid-name
  # ...

```

Les avertissements `pylint` sont chacun identifiés par un nom symbolique
(`empty-docstring`). Les avertissements spécifiques à Google commencent
par `g-`.<br/>

Si la raison de la suppression n'est pas claire à partir du nom symbolique,
ajoute une explication.
La suppression de cette manière a l'avantage que nous pouvons facilement
rechercher les suppressions et les revoir. Tu peux obtenir une liste des
avertissements de `pylint` en faisant :

###### `>_ cmd@01:~$`
```sh
# ~$
pylint --list-msgs
```

Pour obtenir plus d'informations sur un message particulier, utilise :

###### `>_ cmd@02:~$`
```sh
pylint --help-msg=invalid-name
```

Il faut plutôt utiliser `pylint: disable` au lieu d'utiliser l'ancienne forme
dépréciée `pylint: disable-msg`.

Les avertissements concernant les arguments inutilisés peuvent être supprimés
en supprimant les variables au début de la fonction. Il faut  toujours inclure
un commentaire expliquant pourquoi tu les supprime. "Unused." est suffisant.
Par exemple :

###### `</> PYTHON [02]`
```python
def viking_cafe_order(spam: str, beans: str, eggs: str | None = None) -> str:
    del beans, eggs  # Unused by vikings.
    return spam + spam + spam

```

Au fait, s'il y a des arguments d'une fonction que tu n'utilise pas, `pylint`
te mettra des avertissements.<br/>

D'autres formes courantes de suppression de cet avertissement consistent
à utiliser '_' comme identifiant pour l'argument inutilisé ou à préfixer
le nom de l'argument avec 'unused_', ou à les assigner à '_'. Par exemple :

###### `</> PYTHON [03]`
```python
def viking_cafe_order(
  spam: str,
  _beans: str,
  unused_eggs: str | None = None
) -> str:
  # ...

```


Ces formes sont autorisées mais ne sont plus encouragées. Elles brisent
les appelants qui passent les arguments par leur nom et n'imposent pas que
les arguments soient réellement inutilisés.
Elles empêchent l'utilisateur de la fonction de passer les arguments par leur
nom, comme `viking_cafe_order(spam="myspam", beans="ok", eggs=None)`
et ne spécifie pas à l'utilisateur de la fonction que ces paramètres ne sont
plus utilisés.

### 2.2 Importations
Utilisez l'instruction `import` uniquement pour importer les paquets et les
modules, et non pour importer les classes ou les fonctions de façon
individuelles.

#### 2.2.1 Définition
Mécanisme de réutilisation de code d'un module dans une autre.

#### 2.2.2 Avantage
La convention de gestion des espaces de noms est simple. La source de chaque
identifiant est indiquée de manière cohérente; `x.Obj` indique que l'objet
`Obj` est défini dans le module `x`.

#### 2.2.3 Conséquences
Les noms de modules peuvent toujours entrer en collision. Certains noms de
modules sont trop longs pour être utilisés. <!--A expliquer -->

#### 2.2.4 Décision
- Utilise `import x` pour importer des paquets et des modules.
- Utilise `from x import y` où `x` est le préfixe du paquetage et `y` est le
nom du module sans préfixe. Tu sais déjà programmer en python donc pas besoin
de t'expliquer.
- Utilise `from x import y as z` si deux modules nommés `y` doivent être
importés, si `y` entre en conflit avec un nom de premier niveau défini
dans le module actuel, ou si `y` est un nom trop long pour être utilisé.
- Utilise `import y as z` uniquement lorsque `z` est une abréviation standard
(par exemple, `np` pour `numpy`).

Par exemple, le module sound.effects.echo peut être importé comme suit :

###### `</> PYTHON [04]`
```python
from sound.effects import echo

# ...

echo.EchoFilter(input, output, delay=0.7, atten=4)
```

N'utilise pas de noms relatifs dans les importations. Même si le module
se trouve dans le même paquet, utilise le nom complet du paquet.
Cela permet d'éviter d'importer involontairement un paquet deux fois.
<!-- a expliquer -->

##### 2.2.4.1 Exceptions
Exceptions à cette règle:
<ul> 
  <li>Les symboles des modules suivants sont utilisés pour soutenir l'analyse
  statique et la vérification des types:
    <ul>
      <li><a href="#">Le module typing</a></li>
      <li><a href="#">Le module collections.abc</a></li>
      <li><a href="#">Le module typing_extensions</a></li>
    </ul>
  </li>
  <li>Redirection vers le <a href="#">module `typing_extensions`</a></li>
</ul>

### 2.3 Les paquets
Importe chaque module en utilisant le chemin d'accès complet du module.

### 2.3.1 Avantages
Permet d'éviter les conflits dans les noms de modules ou les importations
incorrectes dues au fait que le chemin de recherche des modules ne correspond
pas à ce que l'auteur attendait. Facilite la recherche de modules.
<!-- TODO: A détailler -->

### 2.3.2 Conséquence
Rend le déployement du code plus difficile parce qu'il faut reproduire la
hiérarchie des paquets. Mais grâce aux mécanismes modernes de déploiement,
ce n'est plus un problème.

### 2.3.3 Décision
Tout nouveau code doit importer chaque module par son nom complet.
Les importations doivent être comme suite :

###### `</> PYTHON [05]`
```python
# CODE CORRECT:
# Faire référence à absl.flags dans le code avec le nom complet (verbose).
import absl.flags
from doctor.who import jodie

_FOO = absl.flags.DEFINE_string(...)

```
Ou, encore le code suivant:

###### `</> PYTHON [06]`
```python
# CODE CORRECT:
# Référencer `flags` dans le code avec seulement le nom du module (commun).
from absl import flags
from doctor.who import jodie

_FOO = flags.DEFINE_string(...)

```

*(en supposant que ce fichier de code suivant se trouve dans `doctor/who/` où
  `jodie.py` se trouve également)*
L'importation dans le code source suivant n'est pas correcte.

###### `</> PYTHON [07]`
```python
# CODE PAS CORRECT:
# On ne sait pas exactement quel module l'auteur veut et ce qui sera importé.
# Le comportement réel de l'importation dépend de facteurs externes contrôlant
# sys.path. Quel module possible de jodie l'auteur voulait-il importer ?
import jodie

```

Le répertoire dans lequel se trouve le binaire principal ne doit pas être
considéré comme se trouvant dans `sys.path`, même si c'est le cas dans
certains environnements. Pour cela, le programmeur doit supposer que
`import jodie` fait référence à un module tiers ou de premier niveau nommé
`jodie`, et non à un fichier local `jodie.py`.


### 2.4 Les exceptions
Des exceptions sont autorisées mais doivent être utilisées avec précaution.

#### 2.4.1 Définition
Les exceptions permettent de stopper le flux de contrôle normal, c'est à dire
de l'exécution normale, pour gérer des erreurs ou d'autres conditions
exceptionnelles.

#### 2.4.2 Avantage
Le flux de contrôle du code de fonctionnement normal n'est pas encombré par
le code de traitement des erreurs. Il permet également au flux de contrôle
de sauter plusieurs cadres lorsqu'une certaine condition se produit,
par exemple en revenant de N fonctions imbriquées en une seule étape au lieu
de devoir passer par les codes probablement truffé d'erreur.

#### 2.4.3 Conséquence
Peut rendre le flux de contrôle confus. Il est facile de manquer des cas
d'erreur lors des appels à la bibliothèque. <!-- TODO: a expliquer -->

#### 2.4.4 Décision
Les exceptions doivent respecter certaines conditions :

1. Utilisez les classes d'exception intégrées lorsque cela s'avère utile.
Par exemple, levez une `ValueError` pour signaler une erreur de programmation,
comme une condition préalable non respectée (par exemple, si l'on vous a
transmis un nombre négatif alors que vous aviez besoin d'un nombre positif).
N'utilisez pas les instructions `assert` pour valider les valeurs des
arguments d'une **API publique**. `assert` est utilisé pour garantir la
correction interne, et non pour imposer une utilisation correcte ou pour
indiquer qu'un événement inattendu s'est produit. Si une exception est
souhaitée dans ces derniers cas, utilisez une instruction raise. Par exemple :

###### `</> PYTHON [08]`
```python
# CODE CORRECTE:
def connect_to_next_port(self, minimum: int) -> int:
  """Connects to the next available port.

  Args:
    minimum: A port value greater or equal to 1024.

  Returns:
    The new minimum port.

  Raises:
    ConnectionError: If no available port is found.
  """
  if minimum < 1024:
    # Notez que cette levée de ValueError n'est pas mentionnée dans la 
    # section "Raises :" de la doc
    # dans la section "Raises :" de la doc car il n'est pas approprié de
    # garantir cette réaction comportementale spécifique à une mauvaise
    # utilisation de l'API.
    raise ValueError(f'Min. port must be at least 1024, not {minimum}.')

  port = self._find_next_open_port(minimum)
  if port is None:
    raise ConnectionError(
        f'Could not connect to service on port {minimum} or higher.')

  assert port >= minimum, (
      f'Unexpected port {port} when minimum was {minimum}.')
  return port

```

###### `</> PYTHON [09]`
```python
# CODE PAS CORRECTE:
def connect_to_next_port(self, minimum: int) -> int:
  """Connects to the next available port.

  Args:
    minimum: A port value greater or equal to 1024.

  Returns:
    The new minimum port.
  """
  assert minimum >= 1024, 'Minimum port must be at least 1024.'
  port = self._find_next_open_port(minimum)
  assert port is not None
  return port

```

2. Les bibliothèques ou les paquets peuvent définir leurs propres exceptions.
Dans ce cas, ils doivent hériter d'une classe d'exception existante.
Les noms des exceptions doivent se terminer par `Error` et ne doivent pas
introduire de répétition (`foo.FooError`).

3. N'utilisez jamais d'instructions catch-all `except` : ou catch `Exception`
ou `StandardError`, à moins d'être :
- en soulevant à nouveau l'exception, ou
- la création d'un point d'isolation dans le programme où les exceptions ne
sont pas propagées mais enregistrées et supprimées, comme la protection
d'un thread contre le plantage en gardant son bloc le plus externe.

**Python** est très tolérant à cet égard et except : attrape tout, y compris
les noms mal orthographiés, les appels à sys.exit(), les interruptions Ctrl+C,
les échecs d'unittest et toutes sortes d'autres exceptions que vous ne voulez
tout simplement pas attraper.

4. Minimisez la quantité de code dans un bloc `try`/`except`. Plus le corps
de `try` est important, plus il est probable qu'une exception soit soulevée
par une ligne de code à laquelle vous ne vous attendiez pas. Dans ce cas,
le bloc `try`/`except` cache une véritable erreur.

5. Utilisez la clause `finally` pour exécuter le code, qu'une exception
soit été levée ou non dans le bloc `try`. Cela est souvent utile pour le
nettoyage, par exemple la fermeture d'un fichier.


### 2.5 État global mutable
Éviter les états globaux mutables.

#### 2.5.1 Définition
Valeurs au niveau du module ou attributs de classe qui peuvent être modifiés
au cours de l'exécution du programme.

#### 2.5.2 Avantage
Occasionnellement utile.

#### 2.5.3 Conséquence
- Casse l'encapsulation : Une telle conception peut rendre difficile la
réalisation d'objectifs valables. Par exemple, si l'état global est utilisé
pour gérer la connexion à une base de données, il devient difficile de se
connecter à deux bases de données différentes en même temps (par exemple pour
calculer les différences lors d'une migration). Des problèmes similaires se
posent facilement avec les registres globaux.

- Peut modifier le comportement du module pendant l'importation, car les
affectations aux variables globales sont effectuées lorsque le module est
importé pour la première fois.

#### 2.5.4 Décision
Éviter les états globaux mutables.

Dans les rares cas où l'utilisation d'un état global est justifiée,
les entités globales mutables doivent être déclarées au niveau du module ou en
tant qu'attribut de classe et rendues internes en ajoutant un `_` au nom.
Si nécessaire, l'accès externe à l'état global mutable doit se faire par le
biais de fonctions publiques ou de méthodes de classe. Voir la section
["Nommage"]() ci-dessous. Veuillez expliquer les raisons pour lesquelles
l'état global mutable est utilisé dans un commentaire ou dans un document
lié à un commentaire.

Les constantes au niveau du module sont autorisées et encouragées.
Par exemple : `_MAX_HOLY_HANDGRENADE_COUNT = 3` pour une constante
d'utilisation interne ou `SIR_LANCELOTS_FAVORITE_COLOR = "blue"` pour une
constante de l'API publique. Les constantes doivent être nommées en utilisant
des majuscules et des traits de soulignement. Voir la section
["Nommage"]() ci-dessous.


### 2.6 Classes et fonctions imbriquées/locales/intérieures
Les fonctions ou classes locales imbriquées sont acceptables lorsqu'elles sont
utilisées pour fermer une variable locale. Les classes internes sont
acceptables.

#### 2.6.1 Définition
Une classe peut être définie à l'intérieur d'une méthode, d'une fonction ou
d'une classe. Une fonction peut être définie à l'intérieur d'une méthode ou
d'une fonction. Les fonctions imbriquées ont un accès en lecture seule aux
variables définies dans les champs d'application qui les entourent.

#### 2.6.2 Avantages
Permet de définir des classes et des fonctions utilitaires qui ne sont
utilisées que dans une portée très limitée. Couramment utilisé pour la mise
en œuvre de décorateurs.

#### 2.6.3 Conséquence
Les fonctions et classes imbriquées ne peuvent pas être testées directement.
L'imbrication peut rendre la fonction extérieure plus longue et moins lisible.

#### 2.6.4 Décision
Les fonctions imbriquées sont très bien avec quelques mises en garde.
Éviter les fonctions ou classes imbriquées, sauf pour fermer une valeur locale
autre que `self` ou `cls`. Ne pas imbriquer une fonction simplement pour la
cacher aux utilisateurs d'un module. Au lieu de cela, préfixez son nom par
un `_` au niveau du module afin qu'il soit toujours accessible par les tests.


### 2.7 Comprehensions & Expressions de Generator
C'est bon à utiliser pour des cas simples.

#### 2.7.1 Définition
Les compréhensions `list`, `dict` et `set` ainsi que les expressions
génératrices constituent un moyen concis et efficace de créer des types de
conteneurs et des itérateurs sans avoir recours aux boucles traditionnelles,
aux `map()`, aux `filter()` ou aux `lambda`.

#### 2.7.2 Avantages
Les compréhensions simples peuvent être plus claires et plus simples que
d'autres techniques de création de `dict`, de `list` ou `set`. Les expressions
génératrices peuvent être très efficaces, puisqu'elles évitent la création
d'une liste entièrement.

#### 2.7.3 Conséquence
Les compréhensions compliquées ou les expressions génératrices peuvent être
**difficiles à lire**.

#### 2.7.4 Décision
Bon pour être utilisé pour des cas simples. Chaque portion doit tenir
sur une ligne : *mapping expression*, clause `for`, expression `filter`.
Les multiples clause `for` ou expression `filter` ne sont pas permits.
Utilisez plutôt des boucles lorsque les choses deviennent plus compliquées.

###### `</> PYTHON [10]`
```python
# CODE CORRECT:
result = [mapping_expr for value in iterable if filter_expr]

result = [{'key': value} for value in iterable
          if a_long_filter_expression(value)]

result = [complicated_transform(x)
          for x in iterable if predicate(x)]

descriptive_name = [
    transform({'key': key, 'value': value}, color='black')
    for key, value in generate_iterable(some_input)
    if complicated_condition_is_met(key, value)
]

result = []
for x in range(10):
    for y in range(5):
        if x * y > 10:
            result.append((x, y))

return {x: complicated_transform(x)
        for x in long_generator_function(parameter)
        if x is not None}

squares_generator = (x**2 for x in range(10))

unique_names = {user.name for user in users if user is not None}

eat(jelly_bean for jelly_bean in jelly_beans
    if jelly_bean.color == 'black')

```

###### `</> PYTHON [11]`
```python
CODE PAS CORRECT:
  result = [complicated_transform(
                x, some_argument=x+1)
            for x in iterable if predicate(x)]

  result = [(x, y) for x in range(10) for y in range(5) if x * y > 10]

  return ((x, y, z)
          for x in range(5)
          for y in range(5)
          if x != y
          for z in range(5)
          if y != z)

```


### 2.8 Itérateurs et opérateurs par défaut
Utilisez des itérateurs et des opérateurs par défaut pour les types qui les
prennent en charge, comme les listes, les dictionnaires et les fichiers.


#### 2.8.1 Définition
Les types de conteneurs, comme les dictionnaires et les listes, définissent
des itérateurs par défaut et des opérateurs de test d'appartenance
("in" et "not in").


#### 2.8.2 Avantages
Les itérateurs et opérateurs par défaut sont simples et efficaces.
Ils expriment l'opération directement, sans appel de méthode supplémentaire.
Une fonction qui utilise des opérateurs par défaut est générique.
Elle peut être utilisée avec n'importe quel type prenant en charge l'opération.


#### 2.8.3 Conséquences
Il est impossible de connaître le type d'un objet en lisant le nom
des méthodes (à moins que la variable ne comporte des annotations de type).
Mais cela peut être également un avantage.


#### 2.8.4 Solutions
Utilise les itérateurs et les opérateurs par défaut pour les types qui
les prennent en charge, comme les listes, les dictionnaires et les fichiers.
Les types intégrés définissent également des méthodes d'itérateur. Il faut
préférer ces méthodes à celles qui renvoient des listes, sauf que tu
ne dois pas modifier un conteneur pendant que tu le parcour.

###### `</> PYTHON [12]`
```python
# CODE CORRECTE:
for key in adict: ...
if obj in alist: ...
for line in afile: ...
for k, v in adict.items(): ...

```

```python
# CODE PAS CORRECTE:
for key in adict.keys(): ...
for line in afile.readlines(): ...

```


### 2.9 Générateurs
Utiliser des générateurs si nécessaire.

#### 2.9.1 Définition
Une fonction generator renvoie un itérateur qui produit une valeur chaque fois
qu'il exécute une instruction `yield`. Après avoir produit une valeur, l'état
d'exécution de la fonction generator est suspendu jusqu'à ce que la valeur
suivante soit demandée.

#### 2.9.2 Avantages
Code plus simple, car l'état des variables locales et le flux de contrôle
sont préservés à chaque appel. Un générateur utilise moins de mémoire
qu'une fonction qui crée une liste entière de valeurs en une seule fois.

#### 2.9.3 Conséquences
Les variables locales du générateur ne seront pas libérées jusqu'à ce que le
générateur soit consommé jusqu'à épuisement ou qu'il soit lui-même libéré de
la mémoire.

#### 2.9.4 Solutions
1. Il est recommendé d'utilisez `"Yields :"` plutôt que `"Returns :"`
dans la docstring des fonctions de type générateur.

2. Si le générateur gère une ressource coûteuse, assure toi de forcer
le nettoyage.

3. Une bonne façon de faire le nettoyage est d'envelopper le générateur
avec un gestionnaire de contexte [PEP-0533](https://peps.python.org/pep-0533/).

<!-- https://google.github.io/styleguide/pyguide.html#210-lambda-functions -->


### 2.10 Fonction Lambda
Convient pour les expressions d'une ligne. Préférez les expressions
génératrices avec un lambda que les fonction `map()` ou `filter()`.

#### 2.10.1 Définition
Les **lambdas expressions** définissent des fonctions anonymes dans une
expression.

#### 2.10.2 Avantages
C'est très pratique.

#### 2.10.3 Conséquences
Elles sont plus difficiles à lire et à déboguer que les fonctions locales.
L'expressivité est limitée car la fonction ne peut contenir qu'une seule
expression ou instruction.

#### 2.10.4 Décision
Il est possible de les utiliser pour des définitions d'une ligne d'instruction.
Si le code à l'intérieur de la fonction lambda est plus long que 60-80
caractères, il est préférable de la définir comme une fonction normale.

Pour les opérations courantes comme la multiplication, utilisez les fonctions
du module operator au lieu des fonctions lambda. Par exemple, il faut
préférer `operator.mul` à `lambda x, y : x * y`.


### 2.11 Expressions conditionnelles
C'est bon pour des cas de programmation simple.

#### 2.11.1 Définition
Les expressions conditionnelles (parfois appelées "opérateurs ternaires") sont
des mécanismes qui fournissent une syntaxe plus courte pour les instructions
`if`. Par exemple : `x = 1 if condition else 2`.

#### 2.11.2 Avantages
Plus court et plus pratique qu'une instruction `if` complet.

#### 2.11.3 Conséquences
La condition peut être difficile à localiser ou à percevoir si l'expression
est longue.

#### 2.11.4
Utilisable pour les cas simples. Chaque partie doit tenir sur une ligne :
expression_planA,if condition else expression_plan_B. Il faut utiliser une
instruction `if` complète lorsque les choses deviennent plus complexe.

###### `</> PYTHON [13]`
```python
# CODE CORRECTE:
one_line = 'yes' if predicate(value) else 'no'
slightly_split = ('yes' if predicate(value) else 'no, nein, nyet')
the_longest_ternary_style_that_can_be_done = (
        'yes, true, affirmative, confirmed, correct' if predicate(value)
        else 'no, false, negative, nay'
)

```

###### `</> PYTHON [14]`
```python
# CODE PAS CORRECT:
bad_line_breaking = ('yes' if predicate(value) else 'no')
portion_too_long = (
  'yes' if some_long_module.some_long_predicate_function(
    really_long_variable_name
  )
  else 'no, false, negative, nay'
)

```

<!-- https://google.github.io/styleguide/pyguide.html#212-default-argument-values -->

