# Statistique descriptive
 
 # I.        Mots clés
●	Jeu de données
●	Tendance
●	Brain storming
●	Graphique
●	Le plus adapté au marché
●	paramètres
●	Jeux vidéos (Civ le best)
●	Chiffre d’affaire (PIB du Congo)
## II.Contexte :
Quoi : Choisir le type de jeu
Comment : Toucher population + money
Pourquoi : Stats et étude de marché
 
## III.Contraintes :
●	4 jours
●	Utiliser jeu de données fournis
●	Utiliser un des trois types
 
Problématique : Comment utiliser les stats pour choisir le type de jeu vidéo
## IV.Généralisation :
●	Prise de décision
●	Analyse / Statistiques
## V.Hypothèses :
1.	
 
## VI.Plan d’action :



Bases statistiques :
●	Moyenne
●	Variance
●	Medianne
●	ecarts-types
●	loi (normale...)
●	pValue

loi uniforme :sur le segment [a,b]  f(x) = 1/(b-a) si x est dans [a,b], pour généraliser 
P(x appartenant à a et b

laplace gauss (loi normale) de paramètre (µ, sigma)
f(x) = exp( (-1/2)* ( (x-µ)/sigma)² )/(sigma* racine(2*pi)

null hypothesis significance testing : assume que quelque chose est vrai et montre si on l'assume vrai quelque chose de contradictoire se produit (preuve par contradiction) et on peut la rejeter

proba que si l'hypothèse null ( H_0, aka que ce qu'on dit est faux, et par extension H_1 et ce qu'on veut prouver) est vrai, quelle est la prob d'avoir le résultat obtenu. aka a quel point le résultat sample est rare si l'hypothèse est vrai

one sided p-value ou 2-sided p-value selon si on prend qu'un coté de la courbe ou si on prend sa symétrie (2 sided p-value = 2*1-sided p-value)




●	quartiles
Distribution normale/de poisson

supposons on veut calc X -> N(20;2):
P(x <= 22,42)
P(18 <=x <= 22.4) 
il faut convertir N(20;2) sur la loi normale centrée réduite N(0;1)

on le fait avec T = (X - 20)/2

on  donc P(x <= 22.42) = P( (x-20)/2  <= (22.42 - 20)/2 )
<=> P( T <= 1.21)  = pi(1.21) = 0.8869

pour généraliser

pour calc P( x <= c) ou xsuit la loi normale N(a;b)
on convertic X suivant la loi normale N(a;b) en T suivant la loi normale centrée N(0;1) T= (X-a)/b

on a donc
p(x <= c)  <=> p( T <= (c-a)/b ) = pi(c-a)/b

(cf. doc envoyé par Idoia)


## Chi squared (X² ou Khi deux)

comparaison de proportions, des tests de conformité d’une distribution observée à une distribution théorique et le test d’impédance de deux variables qualitatifs.

test stat qui sépare le signal du bruit

test classique (diff obeservé - expected si null vrai) / average variation

si on veut faire la somme des diff observée on aura tjrs 0 (si on enlève kkpart on ajoute ailleur donc tjrs 0) dnc avant de les aditionner on les élève au carré

somme ( (val observée - val attendue)² / val attendue) 

ce qui donnepar exemple que si on a une éviation de 1, sur un échantillon de 2000 c'est ok mais sur un échantillon de 10 ça peut être important

un degrée de liberté/mouvement? degree of freedom = chaque info (= chaque case du tableau)

forme généralisée  (goodness of fit test)
X² = sum( (O_i - E_i)²/ E_i
E = expected value et O = observed value

il faut tjrs check pour un X²si la fréquence attendue pour chaque case est > 5
si l est plus bas le résultat peut etre arbitraire (et le 5 est choisi arbitrairement mais les statisticiens sont d'accord)

X² test d'indépendance vérif l'indépendance de 2 variables

degré de liberté: (row-1)(colone-1)

pour avoir la fréquence attendue on calcule le %age de la population auquel la case appartient, on fait la somme des valeurs des lignes. et on obtient la fréquence attendue en faisant somme*%age



X² test d'homogénéité: si 2 échantillons viennent de la même source


## régression

GLM general linear model

DATA = model + error(déviation du model, pas forcément problème)
y = b+mx


**régression linéaire**

assume que la relation entre x et y est linéaire
on cherche la ligne la plus proche de tt les points en même temps
<=> minimiser Sum( (Y_i - ^Y)² )

^Y = valeur prédite
_
Y (y barre)= moyenne

SSR : sum of the square for regression = Sum( (^y -ybarre)²)
SST : total sums of squares = SSR+ SSE

TSS = total sum of squares = Sum( (Y_i - ^Y)²)
SSE = Sums of squares for error = SSR-TSS

F-statistic = SSR/SSE mais il faut disiser par les degrées de liberté de chacun donc on a 

***F-stat = (SSR/DF_R)/(SSE/DF_E)***

on met au carré car on veut que les diff positives et négative compte à valeur égales

on appelle aussi les erreurs les residuals et on peut les plot. Idéalement ils doivent être spread, si on voit un patern y a un problème 

F-test : quantifie a quel point la data fit une distribution

F-statistic = (observed model - model if the null is true)/average variation


**k-means**

k est une variable qu'on donne en entrée qui vut dire : sépare les données en k groupe. Il existe également des façon de trouver K 

commence en placant des moyennes a un endroit (en général un des points du jeu de donnée) 
calc la moyenne  des données dans chaque grp (un point est dans le groupe dont il est plus proche du centre de la moyenne choisie) , ca devient la nouvelle moyenne.
On a nos nouvelles moyennes, on repartitionneles groupe avec elles.

MAIS on peut avoir absolument tort, donc on le relance plusieurs fois et on garde la meilleure

on peut évaluer la qualité du clustering avec la variance de chaque cluster et comparer pour les différentes run de k-means la somme de la variance de tous les clusters

la variance va évidement diminuer de façon croissante avec l'augmentation du nombe de cluster, mais le taux de croissance diminue (diminishing return) on obtient un elbow pot

notes: 

pour N vaiables la distance se calculeavec sqrt(var_0²+var_1²+var_2²+...+ var_n²)

en R la fonction kmeans() ajoute des poids à chaque distance
par défaut elle ne test qu'une fois, il faut set nclust pour essayer plusieurs fois (en général 25), ex: kmeans(data, k=3, nclust=25)

## Corbeille
histogramme de déflection, dépouillement, interval de déflection = diagramme bâton

## Objectifs:

Statistique descriptive :

- Définir la statistique descriptive.

- Connaître les notions de population, individu, variable statistique, modalités, variable qualitative et variable quantitative.

- Connaître plus que trois graphiques pour représenter les variables qualitatives.

- Connaître plus que trois graphiques pour représenter les variables quantitatives.

- Connaître plus que trois caractéristiques de tendance centrale plus que trois caractéristiques de dispersion.

Lois de probabilités :

- Connaître plus que trois lois de probabilités.

- Appliquer la loi de probabilité pour déterminer une probabilité (inférence statistique)

Régression linéaire

- Définir une régression linéaire.

- Savoir représenter les données en nuage de points.

- Appliquer la méthode des moindres carrés.

Outils

- Maîtriser le langage R
- WS:
- 
read.xls("C:/Users/Nico/Documents/donnees.xlsx", sheet= 1)

donnee_eau_courant <- donnee_eau[,6]

donnee_eau_courrant_trie <- sort(donnee_eau_courant)

var(donnee_eau_irradiance)
sd(donnee_eau_irradiance)
mean(donnee_eau_irradiance)
quantile(donnee_eau_irradiance)
summary(donnee_eau_irradiance)

 barplot(donne_eau_triee[,6])
 pie(table(donne_eau_triee[,6]))

coraux <- read.xls("C:/Users/Nico/Documents/donnees.xlsx", sheet= "données_coraux")
boxplot(taille_coraux_sorted, horizontal=TRUE)


hist(donnee_eau[,8], prob = TRUE)
 curve(dnorm(x , 252.6, 94.03),from =88, to = 430, add= TRUE)

plot(donnee_eau[,1], donnee_eau[,8], xlab="temp", ylab="sat", main= "sat en fonction de la température")

ggplot(donnes_eau,aes(x=donnes_eau[,1],y=donnes_eau[,8]))+geom_point()+geom_smooth()

 ggplot(donnee_eau,aes(x=donnee_eau[,1],y=donnee_eau[,8]))+geom_point()+geom_smooth(method =lm)
