# What Makes a Penguin? — CRISP-DM on Palmer Penguins

## Links

- 📰 **Blog post (live on GitHub Pages):** https://yradwan147.github.io/palmer-penguins-crispdm/
- 💻 **GitHub repository:** https://github.com/yradwan147/palmer-penguins-crispdm


Final project for Udacity's *Data Scientist Nanodegree* introduction
(nd025). A blog-style walkthrough of CRISP-DM applied to the **Palmer
Penguins** dataset, asking three small business questions and answering
each with a visual + a small model.

## Files

```
penguins_crispdm.ipynb     Executable end-to-end notebook (all 6 CRISP-DM phases as section headers,
                           analysis refactored into docstring-documented functions)
blog_post.md               Medium-style write-up of the findings (with embedded charts)
index.md, _config.yml      GitHub-Pages-rendered version of blog_post.md
images/                    PNG charts referenced by the blog post
```

## CRISP-DM phases

The notebook has explicit section headers for each of the six phases:

1. Business Understanding
2. Data Understanding
3. Data Preparation
4. Data Modeling
5. Evaluate Results
6. Deployment

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
