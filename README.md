# Network Communities: An Interactive Companion

An interactive, single-page web demo that explains community structure in networks, from basic definitions to modern detection algorithms and how to evaluate them.

Created by **Claude Opus 5.5**, based on the lecture slides *"Mesoscale properties of networks: communities"* by **Sang Hoon Lee**.

## Contents

The page follows the order of the lecture, in eleven chapters. Each chapter pairs a short explanation with something you can interact with.

1. **What is a community.** A network with three communities that you can color in.
2. **Inside a community.** Build a community by clicking nodes and watch the internal and external degrees, internal density, and volume update, along with live checks for connected, strong, weak, and clique.
3. **Counting partitions.** Bell numbers on a slider, with how long it would take to check every partition.
4. **Minimum cut.** Move nodes between two sides by hand, see the trivial zero-cut solution, and watch the Kernighan–Lin algorithm find the best bisection.
5. **Hierarchical clustering.** Structural-equivalence (Jaccard) similarity, single, average, and complete linkage, and a dendrogram you can cut at any level.
6. **Girvan–Newman.** Edge betweenness drawn as edge thickness, removed one edge at a time, with a modularity curve to choose the best level.
7. **Modularity.** Paint your own partition of Zachary's karate club and see Q and each community's contribution. Load greedy or Louvain results, change the resolution γ, and compare against a degree-preserving randomization.
8. **Louvain.** Step through the algorithm one node move at a time, see the supernetwork after each aggregation, and reshuffle the visiting order to see its randomness.
9. **Resolution limit.** A ring of cliques where merging pairs of cliques beats keeping them separate, with sliders for ring length, clique size, and γ.
10. **Stochastic block model.** Edit the block matrix and generate community, core–periphery, disassortative, or random structure.
11. **Benchmarks.** The Girvan–Newman planted-partition benchmark, normalized mutual information (NMI), and a sweep showing where detection breaks down.

## Running it

Everything lives in one self-contained file, `index.html`. All algorithms (Louvain, greedy modularity, Girvan–Newman, Kernighan–Lin, hierarchical clustering, SBM sampling, NMI, force-directed layout) are written in plain JavaScript inside the page, with no build step and no framework.

You can open `index.html` directly in a browser, or serve it locally:

```bash
python3 -m http.server
# then visit http://localhost:8000
```

To publish with **GitHub Pages**, push this repository, go to *Settings → Pages*, and choose the branch and root folder that contain `index.html`.

### External resources

The page needs an internet connection for two things. Equations are rendered by [MathJax 3](https://www.mathjax.org/), loaded from jsDelivr. Fonts (Fraunces and IBM Plex Sans) come from Google Fonts. Without a connection, the interactive parts still work, but equations appear as raw LaTeX and system fonts are used instead.

## Features

The layout adapts to phones and tablets, and there is a light and dark theme that follows your system setting or can be switched by hand. Animations are skipped for anyone who has asked their system to reduce motion, and interactive nodes can be reached and activated with the keyboard.

## Data and references

The page uses Zachary's karate club network (as distributed with NetworkX) and synthetic networks generated in the browser. The lecture draws on:

- F. Menczer, S. Fortunato, and C. A. Davis, *A First Course in Network Science* (Cambridge University Press, 2020).
- M. A. Porter, J.-P. Onnela, and P. J. Mucha, "Communities in networks," *Notices of the AMS* **56**, 1082 (2009).
- S. Fortunato, "Community detection in graphs," *Physics Reports* **486**, 75 (2010).
- M. Girvan and M. E. J. Newman, "Community structure in social and biological networks," *PNAS* **99**, 7821 (2002).
- V. D. Blondel, J.-L. Guillaume, R. Lambiotte, and E. Lefebvre, "Fast unfolding of communities in large networks," *J. Stat. Mech.* P10008 (2008).
- M. E. J. Newman, "Equivalence between modularity optimization and maximum likelihood methods for community detection," *Phys. Rev. E* **94**, 052315 (2016).
- S. Fortunato and M. E. J. Newman, "20 years of network community detection," *Nature Physics* **18**, 848 (2022).

## License

No license has been chosen yet. Add a `LICENSE` file before sharing the code for reuse.
