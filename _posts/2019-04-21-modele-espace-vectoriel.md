---
layout: page
title: "Modèle d'espace vectoriel textuel"
---
Salut à tous et bienvenus sur ce nouveau post qui présente des modèles vectoriels textuels.   

### Modèle d'espace vectoriel textuel      
  
Source :**[ From Frequency to Meaning: Vector Space Models of Semantics Peter D. Turney et al.]**    
L'idée de **VSM(Vector Space Models)** est de représenter les documents comme point dans l'espace (un vecteur dans l'espacd). 
Les points prochent dans l'espace sont sémantiquement similaires et les points éloignés sont sémanitquement distants.   
La motivation première de **VSM** est d'utiliser les fréquences de mots dans les corpus de texts pour découvir 
les informations sémantiques.    
     
#### Similarité entre documents: Matrice terme-document    
Lorsque l'on dispose un ensemble de docoments, il peut être organisé sous la forme de matrice **terme-document**; 
dans la quelle les lignes sont les termes( ou mots ) et les colonnes les documents( les pages web par exemple ).
  
#### Définition : sac      
En mathématique un **sac** ( multiset ) est un ensemble ou les doublons sont acceptés et dont l'ordre des éléments 
importe peu; *{a,a,a,b,b,b,c}*  et *{a,b,a,b,c,a,b,b}* sont des **sacs** equivalents et contenant * a, b, c *. 
Un **sac** peut être represente sous forme de vecteur  **x** = <3,3,1> ou le premier 3 est le nombre d'occurences de 
l'élément *a*, le second  3 le monbre d'occurence de l'element *b* et 1 le nombre d'occurence de l'élément *c*.  
Un ensemble de **sac** peut être représenté par une matrice **X**, ou  chaque colonne   *x_{:j}* correspond à un **sac** 
, haque ligne *x_{i:}* correspond à un élément unique  et *x_{i,j}* correspond à la fréquence du  *i*eme élément dans le 
*j*eme **sac**.    
Dans la matrice **terme-document**, le vecteur document représent le dit document comme un **sac a mot**.   

#### Hypothèse du sac à mots
Dans le domaine de la recherche d'information, cette hypothèse stipule que on peut estimer l'importance d'un document 
par rapport à une requête en représentant le document et la requête en **sac à mots** c'est à dire que les fréquences de 
mots dans un document indique l'importance du dit document par rapport à la requête; en d'autre terme, le vecteur 
colonne du la matrice *terme-document* exprime à un certain degré à ceux à quoi renvoit le document.  
Soit **X** une matrice *terme-document* d'une collection contenant *n* document de *m* unique mots distincts 
( le vocabulaire ), la matrice aura *m* lignes et *n* colonnes. Soit *w_{i}* le *i*eme mot dans le vocabulaire et 
*d_{j}* le *j*eme document dans la collection, le vecteur ligne de **X** (*x_{:j}*) contient *n* éléments correspondants 
à la fréquence du *i*eme mot du vocabulaire dans chaque document, c'est aussi la **signature** de ce mot et le 
vecteur colonne de **X** (*x_{i:}*) contient *m* éléments représentants la fréquence de chaque élément du vocabulaire 
dans le *i*eme document, c'est aussi la signature de ce docuement.  
L'élément *x_{ij}* de la matrice **X** est la frequence du *i*eme terme dans le *j*eme document.  
Toute fois, bien que cette représentation pour chaque document donne la fréquence des mots dans ce document, cette 
représentation perd l'ordre de la sequence de ces mots dans le document ainsi que la structuration du document ( les 
phrases, les paragraphes, les sections, les chapitres).  
Néanmoins cette représentation capte bien certain aspect de la sémantique.  

#### Similarité des mots: Matrice terme-context
Selon les auteurs, l'importance d'une requête, par rapport à un document est donnée par la similarité entre le vecteur 
du document et celui de la requête.  
D'autre part les auteurs Deerwester et al. (1990) disent qu'au lieu de regarder la similarité entre les documents, on 
peut regarder la similarité entre les mots ou termes en prennant en considération le ligne au lieu des colonnes de la 
matrice terme-document.  
Deerwester et son équipe s'inspire de la matrice terme-document en évoquant le fait que la taille du document n'est pas 
forcement la longueur ideale pour pour la messure de similarité. De ce fait, ils proposent la matrice terme-contexte ou 
le contexte peut etre des mots, des phrases, des paragraphes ou des documents.  

#### Hypothèse de distributivité 
En linguistique cet hypothèse stipule que les mots qui apparaissent dans les contextes similaires ont tendance à avoir 
le même sens(Harris, 1954).  
C'est cette hypothese qui justifie l'utilisation du VSM pour mesurer la similarité entre les mots. Pour ce qui est de 
la représentation terme-contexte, la représentation vectorielle d'un mot permet deriver de la co-occurance du mot avec 
des contexte variés comme les fenêtres de mots, les dépendances grammaticales... . les lignes de vecteurs similaire de 
la matrice terme-contexte indique les mots ayant des sens similaires.  
      
#### Similarité entre les relations: Matrice des pair-pattern
Dans la matrice pair-pattern, les vecteurs lignes correspondent aux paires de mots comme *mason:stone*, *carpenter:wood* 
et les vecteurs colonnes correpondent aux patterns dont les paires apparaissent, comme *X cuts Y*, *works with Y*.  
      
      
      
      