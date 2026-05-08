# What Makes a Penguin? — CRISP-DM on Palmer Penguins

Final project for Udacity's *Data Scientist Nanodegree* introduction
(nd025). A blog-style walkthrough of CRISP-DM applied to the **Palmer
Penguins** dataset, asking three small business questions and answering
each with a visual + a small model.

## Files

```
penguins_crispdm.ipynb     Executable end-to-end notebook (CRISP-DM phases)
blog_post.md               Medium-style write-up of the findings
```

## Libraries

* pandas, numpy
* seaborn, matplotlib
* scikit-learn (`RandomForestClassifier`, `train_test_split`,
  `cross_val_score`, `classification_report`)

## Findings

1. **Where do they live?** Adelie are everywhere; Chinstrap are
   Dream-only; Gentoo are Biscoe-only.
2. **What separates the species?** Bill length splits Adelie vs
   Chinstrap/Gentoo, bill depth splits Gentoo vs the others; flipper
   length and body mass put Gentoo well clear.
3. **Can we predict species?** Yes — a 4-feature random forest gets
   ~99 % 5-fold-CV accuracy. Bill length is the most important feature.

The blog post is written in a non-technical voice for a manager-style
audience; the notebook has the executable code with documented
assumptions.

## Acknowledgements

* Dataset: [Palmer Penguins](https://allisonhorst.github.io/palmerpenguins/)
  (licensed CC-0).
* Loaded via `seaborn.load_dataset("penguins")`.

## License

Educational submission for Udacity nd025.
