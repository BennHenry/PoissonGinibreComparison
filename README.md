# Critical-radius comparison for Ginibre and Poisson percolation

A collaborative study of how repulsion between random points affects connectivity. We place a disk of the same radius around every point and ask how large that radius must be for the disks to form an unbounded connected region. We compare two random point configurations with the same average number of points per unit area: Ginibre and Poisson.

Every result, method, or proof on this Git repository is completely free to reuse. If you want to take it, write your own article, and add to the noise, you are free to do so. However, we believe that the current capabilities of AI should push us toward a more collaborative, less ego-driven way of doing mathematics. We generally believe that there is no point in claiming for yourself results that are or can be easily AI-generated (more info in the [manifesto](A%20Manifesto%20for%20Renewing%20the%20Practice%20of%20Mathematics.pdf)). So we advise against participating in the noise and invite you to join us. You are very welcome.

It is still not very clear how we will work together, but there is a [Discord server available for discussion](https://discord.gg/fcsYGk7NT).

The final aim is to build a coherent, checked, reader-friendly account of the mathematics: what is known, which arguments work, and which questions remain. The ultimate goal could be a future manuscript under a collective name, online videos, or anything that allows us to share this mathematics. All of this comes with the idea of rejecting ownership of results or proofs, as well as individual credit.

## Models and main question

The two point processes are normalized to have an expected one point per unit area:

* **Poisson, written $\Pi_1$.** The number of points in a region has a Poisson distribution with mean equal to its area. Counts in disjoint regions are independent.
* **Ginibre, written $G$.** Points repel one another, so very close pairs are less common. This process arises from the eigenvalues of large random matrices with independent complex Gaussian entries, observed in the interior of the eigenvalue distribution and scaled to have the same mean density as $\Pi_1$.

Around each point, draw a closed disk of radius $r$. Two disks overlap when their centers are at distance at most $2r$. The union **percolates** if it contains an unbounded connected component. The **critical radius** $r_c$ is the infimum of the radii for which this happens with positive probability.

The main question is whether

$$
r_c(G)<r_c(\Pi_1).
$$

In other words, does the more regular spacing caused by Ginibre repulsion allow an unbounded connection using strictly smaller disks? The supplied investigation does not settle this inequality.

## History

This project starts from an investigation report dated 15 September 2026, a coverage audit dated 21 September 2026, and an amended report incorporating additional arguments. These materials are preserved in [Raw Material](Raw%C2%A0Material/). The amended report is the default manuscript for this repository.

## Announced results

Announced results are results claimed to be proved in the supplied reports but that have not yet been checked or rewritten by this project.

* **A comparison after randomly removing points.** Keep each Ginibre point independently with probability $\beta\in(0,1)$, then multiply its coordinates by $\sqrt\beta$ to restore mean density one. Call the resulting process $G_\beta$. The report shows that it can be constructed together with a Poisson process so that every point of $G_\beta$ belongs to the Poisson configuration. The smallest possible Poisson density in such a construction is $L_\beta=-\log(1-\beta)/\beta$. This gives the lower bound $r_c(G_\beta)\ge r_c(\Pi_1)/\sqrt{L_\beta}$ ([amended report](Raw%C2%A0Material/ginibre_poisson_investigation_2.tex)).
* **Strong stretching leads to Poisson behavior.** Stretch the Ginibre configuration in one direction and compress it by the reciprocal factor in the perpendicular direction, preserving area and mean density. As the stretching grows, the distribution in any fixed bounded region approaches that of Poisson. The report also proves that the critical radius approaches the Poisson critical radius ([amended report](Raw%C2%A0Material/ginibre_poisson_investigation_2.tex)).
* **An exact formula for changing the proportion of Ginibre and Poisson points.** Independently keep a fraction of the Ginibre points and add an independent Poisson process to maintain mean density one. The report gives a derivative formula for the probability of a connection event in a bounded region as this fraction varies. It distinguishes two effects: two added points can either provide alternative connections or both be needed for one connection. Controlling their balance remains a difficulty ([amended report](Raw%C2%A0Material/ginibre_poisson_investigation_2.tex)).
* **Bounds after observing distant points.** After revealing all points outside a disk, the report bounds the probability of finding points in a smaller region strictly inside that disk. The gap between the region being studied and the observed exterior is essential to the stated estimate ([amended report](Raw%C2%A0Material/ginibre_poisson_investigation_2.tex)).
* **Some proposed shortcuts fail.** The report gives counterexamples to intermediate estimates intended to compare connection probabilities. For example, certain estimates cannot hold uniformly over all configurations observed outside a region. These counterexamples rule out particular proof strategies; they do not settle the critical-radius inequality ([amended report](Raw%C2%A0Material/ginibre_poisson_investigation_2.tex)).

The report also preserves an argument predicting $r_c(G_\beta)=r_c(\Pi_1)(1-\beta/4)+o(\beta)$ as $\beta$ tends to zero, where the error divided by $\beta$ tends to zero. In this regime, most Ginibre points have been removed and the rescaled process is close to Poisson. A geometric estimate needed for this argument remains to be fully verified, so the expansion is not listed here as an established result. Even if verified, it would not by itself settle the question for the original Ginibre process, which corresponds to $\beta=1$.

## Checked results

No results are yet recorded here as checked by the collaborative project. The reports contain their own verification labels; these are part of the research record. The initial task is to review those proofs and the dependencies identified by the coverage audit.

## Open questions

* **Does Ginibre percolate with strictly smaller disks than Poisson?** Prove or disprove $r_c(G)<r_c(\Pi_1)$ at equal mean density.
* **Can the proposed expansion for $G_\beta$ be proved?** Complete the geometric estimate needed when the retained fraction $\beta$ is small. Then determine whether a comparison can be extended towards $\beta=1$.
* **Can estimates in bounded regions prove an unbounded connection?** One proposed route is to show that Ginibre disks connect across sufficiently large rectangles often enough at a radius strictly below $r_c(\Pi_1)$. The report gives a criterion for turning such estimates into percolation, but does not establish the required bounds for Ginibre.

## Repository contents

| File | Role |
| --- | --- |
| [Amended report](Raw%C2%A0Material/ginibre_poisson_investigation_2.tex) | Default manuscript, amended 21 September 2026. |
| [Original report](Raw%C2%A0Material/ginibre_poisson_investigation.tex) | Earlier account, preserved with its [supplied PDF](Raw%C2%A0Material/ginibre_poisson_investigation.pdf). |
| [Coverage audit](Raw%C2%A0Material/report_coverage_audit.md) | Records material omitted or compressed in the original report. |
| [main.tex](main.tex) | Working entry point, initially including the amended report. |
| [Manifesto](A%20Manifesto%20for%20Renewing%20the%20Practice%20of%20Mathematics.pdf) | Shared motivation for these open mathematics projects. |

The reports and audit refer to a larger archive of source notes and a reference inventory that are not included in the supplied folder. Those historical references are preserved as received.

## Building the notes

With `make`, `latexmk`, and a TeX Live installation providing the packages used by the reports, run from this directory:

```sh
make manuscript
make working
```

The outputs are `build/manuscript/ginibre_poisson_investigation_2.pdf` and `build/working/main.pdf`. Running `make` alone builds the manuscript.

Build output and TeX auxiliary files are ignored by Git. The supplied original PDF and the manifesto remain eligible for tracking. Each project is an independent repository.

## Disclaimer

By participating in this project, you withdraw any claim of ownership over the results that you provide. We believe that ownership of a proof or a mathematical result has become a nonsensical concept and, as such, should be rejected.

The repository uses the same [MIT license](LICENSE) as UniDLR.

## Working principles

* Not clear at the moment. It will depend on the dynamics of the group.
