# What Makes a Penguin? Three Questions on the Palmer Penguins

> *Cover image idea: a side-by-side photo of an Adélie, a Chinstrap and a
> Gentoo penguin from the Palmer LTER programme.*

The Palmer Penguins dataset has 344 rows of body measurements for three
penguin species across three Antarctic islands. It's a friendly little
dataset — small, clean enough to load in one line, and famously cited
as the "iris but for the 2020s." I used it to walk through the
CRISP-DM data-science process, asking three questions every employer
asks: **who, what, and can we predict?**

## 1. Who lives where?

The first question I asked was simply where each species hangs out.
Crossing species against island gives a clean three-row picture:

| species   | Biscoe | Dream | Torgersen |
|-----------|-------:|------:|----------:|
| Adelie    | 44     | 56    | 52        |
| Chinstrap | 0      | 68    | 0         |
| Gentoo    | 124    | 0     | 0         |

Two of the three islands have a "second species" you can recognise
just by location — Chinstrap is exclusive to Dream and Gentoo is
exclusive to Biscoe. Adelie penguins, on the other hand, are the
democrats of the Palmer archipelago: they're on every island.

## 2. What does the body of each species look like?

The pairplot of the four numeric measurements
(`bill_length_mm`, `bill_depth_mm`, `flipper_length_mm`, `body_mass_g`)
makes this almost too obvious. Gentoo are the long-flipper, big-body,
shallow-bill outliers. Chinstrap and Adelie are similar in size and
flipper length, but Chinstrap have noticeably longer bills.

The pair `bill_length_mm × bill_depth_mm` alone gives a near-perfect
2-D separation between all three species — you can almost draw the
decision boundary by hand.

## 3. Can a model predict species from body measurements alone?

Yes. A random-forest classifier with 300 trees trained on the four
numeric features hits ~99 % five-fold-CV accuracy. **Bill length** is
by far the most informative feature; **flipper length** is the
second; **body mass** adds the least.

If you wanted a smaller, interpretable model, two features
(`bill_length_mm`, `flipper_length_mm`) and a depth-3 decision tree get
you to ~96 % accuracy with a tree any biologist could read.

## Take-aways

* CRISP-DM works even on a small dataset — the structure forces you to
  ask "what does the business want," not just "what does the data say."
* Categorical and numeric features answer **different** questions:
  island gives location, body measurements give species; together
  they're stronger than either alone.
* When 99 % accuracy comes from a tree with four splits, the
  interesting work is in the **explanation**, not the **architecture**.

The notebook ([`penguins_crispdm.ipynb`](penguins_crispdm.ipynb)) has
the full code, plots, and tables.
