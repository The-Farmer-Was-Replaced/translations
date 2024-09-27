# Déverrouillages Automatiques

Pour automatiser complètement le jeu, vous pouvez utiliser la fonction `unlock()` pour déverrouiller automatiquement les fonctionnalités.

Par exemple, vous pouvez utiliser `unlock(Unlocks.Speed)` et `unlock(Unlocks.Expand)` pour déverrouiller les fonctionnalités de vitesse et d'expansion.

Pour déterminer le coût d'un déverrouillage, utilisez simplement la fonction `get_cost()` comme vous le feriez pour une plante ou un article.

Exemple :
`get_cost(Unlocks.Loops)`
renvoie `{Items.Hay:5}`

Si vous souhaitez savoir combien de fois un déverrouillage particulier a été effectué, utilisez la fonction `num_unlocked(unlock)`.

Par exemple, `num_unlocked(Unlocks.Speed)` renverra le nombre de mises à niveau de vitesse que vous avez.

`num_unlocked(Unlocks.Senses)` renverra `1` si les sens sont déverrouillés et `0` s'ils ne le sont pas.

Vous pouvez également utiliser `num_unlocked()` sur les Items, Entities ou Grounds. Cela renverra `1` si c'est déverrouillé, sinon `0`.

Faites attention, `num_unlocked(Unlocks.Carrots)` renverra le nombre de fois où il a été déverrouillé/amélioré.
`num_unlocked(Items.Carrots)` ne renverra que `0` ou `1`. (Même chose pour les autres plantes)