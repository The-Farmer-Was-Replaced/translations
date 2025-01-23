# Fertilizer

À un certain moment, attendre la croissance des plantes ne suffit plus.
Comme pour l’eau, tu reçois automatiquement 1 engrais toutes les 10 secondes, plus un supplémentaire pour chaque amélioration.

L’engrais fait pousser instantanément les plantes. `use_item(Items.Fertilizer)` réduit le temps de croissance restant de la plante sous le drone de 2 secondes.

Cela entraîne certains effets secondaires.
Les plantes cultivées avec de l’engrais seront infectées.

Lorsqu’une plante est infectée, la moitié de sa récolte est convertie en `Items.Weird_Substance` lorsqu’elle est récoltée.
Weird Substance peut également être utilisée sur des plantes, ce qui a pour effet d’activer ou de désactiver l’état d’infection de la plante et de toutes les plantes adjacentes.

Ainsi, si tu exécutes `use_item(Items.Weird_Substance)` sur une plante infectée, tu la soigneras, mais si tu l’utilises sur une plante saine, tu l’infecteras.

Si tu l’utilises sur une plante infectée qui a des voisines saines, tu soigneras cette plante tout en infectant les voisines, et inversement.
