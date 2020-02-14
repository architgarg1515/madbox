# Test de Data Analyst pour Madbox

## Analyse des données

Pour ce test, j'ai tout d'abord vérifié la tendances des données. J'ai pu observer qu'il y avait deux tendances qui se détachaient : des courbes semi-constantes (ecpm et margin, qui ont un écart-type assez faible) et des courbes logarithmiques. 

A la vue de ces résultats, j'ai décidé de partir sur un modèle ARIMA, qui permet de travailler sur des séries temporelles. 

## Explication de la technique utilisée

Le modèle ARIMA permet de travailler sur des données non-stationnaires (ce qui est notre cas ici). En se basant sur la moyenne mobile de nos données, le modèle nous autorise à travailler avec une variation saisonnière.

J'ai commencé par prédire l'utilisation du modèle ARIMA sur nos données. La tendance semblait suivre correctement les observations.

J'ai donc découpé ensuite les données en deux parties, 80% de l'échantillon sert d'entraïnement au modèle et le reste permettra de vérifier si notre modèle est correct. Les résultats de ce test semblent adéquats avec l'échantillon de test.

## Améliorations et limites

Cette méthode a l'avantage d'être plutôt simple, en ne prenant en compte qu'une seule entrée (ici on a travaillé uniquement sur les profits). Il permet de prédire assez facilement une évolution des gains.

Le choix a été fait ici de ne pas prendre en compte la saisonnalité des revenus, ce qui explique une courbe "lisse" et un intervalle de confiance assez grand. 

Une autre méthode que j'aurais pu utiliser est la prédiction des spends. Grâce à cela, j'aurais pu :
- estimer le nombre d'impression (il y a une corrélation à 97% entre ces deux variables)
- estimer le revenue (revenue = (nb_impressions/1000) x ecpm)
- calculer le profit (profit = revenue x margin) 

Cette méthode permet de travailler à la base avec la variable qui est maitrisé par l'entreprise mais elle peut induire un biais en estimant le reste des variables.

## Temps passé

J'ai travaillé sur le projet 3 soirs de cette semaine, à raison de 2 à 3 heures par soir. J'ai donc dû travailler environ 10h dessus.