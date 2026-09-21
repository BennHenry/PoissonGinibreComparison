# Coverage audit of ginibre_poisson_investigation.tex

Date: 21 September 2026. The report and all archived sources were left unchanged.

**Conclusion: the report does not present all the discoveries in the supplied sources.** It preserves the main narrative and many important theorems, counterexamples, and limitations. However, several substantial results are only listed in its source index or mentioned through a filename. Other branches are summarized without their strongest quantitative conclusions.

This is a **coverage audit**, not a fresh certification of every mathematical proof. “The source derives” below describes what the archived source contains. An omitted result could be restored as a recovered argument with its dependencies stated; completeness does not require adopting every historical “proved” or “audited” label.

## Scope and checks

- The manifest has 137 entries. Every archived file exists and its SHA-256 matches the manifest.
- All 130 individual Markdown notes are listed in the report’s source index.
- The historical checkpoint contains 128 proof-note appendices, each preserving the corresponding individual note’s text. The other two individual notes are checkpoint/front documents.
- The comparison used the report’s mathematical sections, the individual notes and their audits, the historical accounts, and the two attachments. Duplicate checkpoint descriptions were not counted as new discoveries.
- A filename citation was not counted as presentation of that file’s mathematical conclusions.
- The companion [reference inventory](source_reference_inventory.tsv) records filename-level coverage for every individual note. Its flags are mechanical reference checks, not mathematical coverage scores.

The findings below establish noncompleteness. They are a documented list of substantive gaps, not a claim that every omitted intermediate estimate or proof detail has been enumerated.

## Substantive missing or incomplete results

### 1. The quantitative stretching-limit rate is missing

**Source:** [ellipse_critical_variation.md, §4](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/ellipse_critical_variation.md:156>), supported by [its audit](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/ellipse_critical_variation_audit.md:28>).

For \(c(t)=r_c(S_t^{-1}G)\), the source derives
\[
 |c(t)-r_P|\le C t^{-\eta/2}
\]
for sufficiently large \(t\). It combines the local total-variation estimate at block size proportional to \(\sqrt t\), a published near-critical Poisson input, and the negative-association block criteria. It also specifies how a finite-deformation orientation advantage exceeding this error would imply a strict radius gap.

**Report:** [the stretching-limit theorem and its scope](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:1137>) give convergence, and [lines beginning at 1226](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:1226>) explicitly say that the displayed proof supplies no rate. The separate source argument for a rate is not presented or assigned a verification status.

**Assessment:** a stronger source conclusion is omitted. The report’s statement about its own qualitative proof is not itself a contradiction. Restoring the rate requires retaining its additional near-critical input and the source’s qualification about that published proof.

### 2. The exact critical-radius orientation identity and further shape calculations are missing

**Source:** [ellipse_critical_variation.md, §§1–3](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/ellipse_critical_variation.md:9>).

The source introduces fixed center terminals and proves the finite-threshold identity
\[
 U'(t)=-U(t)\cos(2\Theta(t))\mathbf1_{\{U(t)<R\}},
\]
the contact formula \(\partial_t C=rM\,\partial_r C\), and a uniform diagonal passage yielding
\[
 c(T)-c(0)=-\lim_n\int_0^T
 \mathbb E[U_n(t)\mathbf1_{\{U_n(t)<R\}}\cos(2\Theta_n(t))]\,dt.
\]
It also localizes the surviving contribution near the critical radius.

Further source calculations include the [rotation-invariant Riesz-kernel coefficient](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/ellipse_critical_variation.md:245>)
\[
 -\frac1{2\pi}\iint |x-y|^{-1}\mathbb E_\Pi[D_xD_yF]\,dx\,dy
\]
and the [two-point Palm contact response](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/ellipse_critical_variation.md:311>), whose explicit pair-density contribution is \(v/(e^v-1)>0\), \(v=4\pi r^2\).

**Report:** [the ellipse perturbation subsection](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:1304>) presents the covertical finite-window coefficient, and [the affine survey](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:2539>) presents opposite crossing signs. It does not present these additional identities or the explicit Palm-response term.

**Assessment:** partial coverage of the shape branch, with important exact reductions absent. These are not favorable-sign theorems.

### 3. The bottleneck switching and negative-curvature discoveries are missing

**Source:** [ellipse_minmax_switching.md](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/ellipse_minmax_switching.md:5>).

The source calculates the switching measure in the distributional second derivative of a minimax threshold, constructs complete Euclidean graphs with switching atoms of both signs, and shows that rotation averaging can preserve cusps. Its smooth isotropic finite-law example satisfies
\[
 M''(0)=\tfrac32M(0)-\tfrac{16}{25}h(0)<0
\]
for an appropriate density \(h\), despite almost-sure absence of fixed-time ties and positive curvature of each edge.

**Report:** [the filename is cited](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:3607>), but the switching identity and examples are absent. The isotropic cluster-process counterexample and the two-insertion bottleneck example elsewhere in the report concern different assertions.

**Assessment:** a distinct obstruction to the shape-convexity route is omitted.

### 4. The sharp coupling barriers from small beta to full Ginibre are missing

**Source:** [research/ginibre_coupling_bridge_obstructions.md](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/research/ginibre_coupling_bridge_obstructions.md:9>).

The source derives several separate conclusions:

- Inclusion of the intensity-\(\lambda\) beta-Ginibre process in unit-intensity full Ginibre requires \(\lambda\le\beta\), using coalescing factorial densities.
- The same restriction holds for any injective coupling with an arbitrary fixed finite displacement bound, using a disk overcrowding expansion through its \(n^2\) term.
- Even allowing collisions in a directed covering map does not permit the needed near-identity transfer. For \(\beta\le1/10\), \(\lambda\le1\), its necessary inequality is
  \[
  e^{-10/9}-2e^{-2}\le1-\lambda+2\pi D^2+2\sqrt\pi D.
  \]
- Independent superposition and orthogonal spectral decomposition do not supply the proposed inclusion shortcut.

**Report:** [the small-beta endpoint discussion](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:2357>) states the loss from ordinary thinning. It does not state that dependent inclusion and bounded-displacement injections face the same sharp barrier, or give the noninjective obstruction. The source appears [in the index](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:3974>).

**Assessment:** a major family of negative discoveries is omitted; these results explain why several possible continuations of the small-beta result cannot work.

### 5. The strict positive-bath mixed-model comparison is not stated

**Source:** [positive_bath_pde_comparison.md](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/positive_bath_pde_comparison.md:3>), especially [its quantitative conclusion](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/positive_bath_pde_comparison.md:109>).

For a fixed Poisson fraction \(a\in(0,1)\), the source’s unit-intensity mixed model is
\[
 Y_{\beta,a}=\operatorname{DPP}(\beta(1-a)H_\beta)\cup\Pi_a.
\]
Subject to the stated uniform differential input, it derives
\[
 r_c(Y_{\beta,a})\le r_P-\frac{r_P(1-a)^2\beta}{32}<r_P
\]
for sufficiently small beta, with an explicit effective intensity and radius drift.

**Report:** [the small-beta section](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:2217>) cites this source for a characteristic-integration technique, and the branch survey discusses positive-bath estimates. The separate mixed-model theorem, model definition, and quantitative gap are absent.

**Assessment:** a substantive positive result is omitted. It must retain its dependence on the uniform differential estimate; it is not the pure small-beta theorem.

### 6. The established conditional clearing laws are largely missing

**Sources:** [count_preserving_corridor_clearing.md](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/count_preserving_corridor_clearing.md:107>), [its count integration and exterior normalization](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/count_preserving_corridor_clearing.md:197>), and [count_preserving_annular_clearing.md](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/count_preserving_annular_clearing.md:88>).

These sources derive Brownian-exit, count-preserving event comparisons with constants independent of corridor length or annulus radius. With the stated all-output geometric condition, they obtain
\[
 \mathbb P(F_{\rm target}\mid\mathrm{exterior})
 \ge C^{-n}\mathbb P(E\mid\mathrm{exterior}),\qquad
 \mathbb P(F_{\rm target})\ge\mathbb E[C^{-N(V)}\mathbf1_E].
\]
A genuinely exterior source event admits an \(\exp(-c|V|)\) relative cost. The annular construction gives an explicit constant and a separated-terminal geometry for which every output preserves the required nonconnection/pivotality.

Separately, [the corridor spectral source](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/research/rare_pivotal_weighting_and_corridors.md:204>) derives an actual buffered conditional hole lower bound
\[
 \mathbb P(N(D)=0\mid\mathrm{outside}\ B_R)
 \ge\exp[-4|D|/(1-\kappa_w)]
\]
under its stated buffer and strip conditions.

**Report:** [the corridor paragraph](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:3312>) records the strip norm and says it suggests a suitable void cost. It does not present that conditional theorem, the Brownian-exit event comparisons, or the annular repair. The corridor-clearing filename appears in the source map.

**Assessment:** positive intermediate results are omitted while the unsolved filling problem is retained. Clearing does not by itself solve generic pivotal filling; that limitation should remain.

### 7. The fixed-kernel Poisson expansion is only partially covered

**Source:** [research/fixed_kernel_poisson_second_variation.md](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/research/fixed_kernel_poisson_second_variation.md:9>).

The report does retain \(C'(0)=0\) and the Gaussian second-variation integral in [the fine-mesh discussion](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:2843>). Missing from the presentation are:

- the entire factorial-difference expansion for \(\operatorname{DPP}(sH_1)\cup\Pi_{1-s}\) and its explicit fixed-window remainder;
- the joint lens calculation that succeeds where separately saturated movement and cooperation bounds fail;
- [a positive family with arbitrarily long arms and the full neutral Poisson background retained](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/research/fixed_kernel_poisson_second_variation.md:353>);
- [the extension to the actual seed and outer terminal with explicit Gaussian tail errors](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/research/fixed_kernel_poisson_second_variation.md:430>).

**Assessment:** the basic derivative is covered, but important later discoveries are missing. This positive family is different from the full-Ginibre Fock-resolvent ray family that the report does describe. Neither proves positivity of the full pivotal average.

### 8. Finite-rank residual-projection dynamics is absent from the mathematical account

**Source:** [residual_projection_dynamics.md](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/residual_projection_dynamics.md:1>).

The source derives the exact reveal-process birth intensity \(Q_\eta(z,z)/(1-s)\), the squared-kernel evolution, and
\[
 M_p(s)\le M_p(0)\quad(0<p\le1),\qquad
 M_2(s)\le\frac{M_2(0)}{(1-s)^2}.
\]
It computes \(M_2(0)=2N\beta/\pi\) and the total Papangelou influence \(s/(1-s)\), yielding a Hamming-disagreement contraction bound when \(s<1/2\).

**Report:** [the source index](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:3982>) names the note. The reversible one-point move in the body is a different construction and does not present these results.

**Assessment:** a distinct collection of finite-rank dynamical identities and bounds is omitted. Its unweighted, finite-rank scope is essential.

### 9. The endpoint-uniform protected close-pair estimate is missing

**Source:** [pivotal_close_pair_estimate.md, §3](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/pivotal_close_pair_estimate.md:67>).

A consecutive internal DPP pair at separation at most delta forces two opposite shell neighbors. The Bergman repair retains pair repulsion and yields an exterior-event-weighted bound proportional to
\[
 \delta^6\,\mathbb P(E_{\rm ext}),
\]
with constants uniform through \(s=1\).

**Report:** [conditional Bergman bounds](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:427>) and various shell arguments are present, but this four-point, sixth-power consequence is not. It is distinct from the small-beta \(d^3\) pivotal-root estimate.

**Assessment:** a quantitative local discovery is omitted. The source itself leaves conversion from \(E_{\rm ext}\) to actual pivotality unresolved and records submission for independent audit.

### 10. Several genuine-Palm-relocation results are missing

**Source:** [ginibre_palm_relocation_markov.md, §§6–8](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/ginibre_palm_relocation_markov.md:195>), with [the local independent audit](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/palm_relocation_local_independent_audit.md:7>).

Beyond the exact Goldman normalization, the source derives:

- a measurable insertion construction inside \(B(q,R)\), whose reconstructed law differs from ordinary Ginibre by total variation at most \(e^{-\pi R^2}\);
- impossibility of a row-normalized holomorphic-square deletion-weight representation;
- forced nodal zeros for continuous correct deletion weights;
- impossibility of the corresponding positive-operator measurement representation.

**Report:** [the Goldman discussion](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:3472>) includes genuine insertion weights, annealed column balance, and the finite-rank Lagrange counterexample. It omits the above additional construction and no-go results.

**Assessment:** partial coverage. The local approximation has an absolute error, not a relative rare-pivotal error; the representation obstructions do not rule out general measurable Goldman weights.

### 11. The Steiner certificate theorem and exact local capture are missing

**Source:** [research/steiner_certificate_clique_excess.md](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/research/steiner_certificate_clique_excess.md:7>), especially [the local capture result](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/research/steiner_certificate_clique_excess.md:103>).

The source proves that a minimal induced connected graph containing \(k\) prescribed vertices can be made triangle-free by deleting at most \(k-2\) exceptional vertices. Its two-terminal application gives a cap-two certificate plus a controlled finite exceptional set. For the full augmented certificate,
\[
 B_A\cap B(q,L_0-R_0)
 =\operatorname{Piv}(\eta)\cap B(q,L_0-R_0).
\]

**Report:** [the multipair discussion](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:3350>) mentions augmented certificates and exceptional vertices without the graph theorem or this exact capture identity.

**Assessment:** a constructive combinatorial discovery is omitted. The exceptional-set deletion is for counting/analysis and need not preserve connectivity.

### 12. The buffered conditional density-gap strengthening is missing

**Source:** [research/induced_certificate_density_gap.md, §§5–6](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/research/induced_certificate_density_gap.md:163>).

Besides the unconditional cap-two density gap, the source derives a quantitative approximation of the buffered Bergman diagonal to one and, for every event \(E\) observed outside a sufficiently larger disk,
\[
 \mathbb P(E\cap\{\text{bad capped density in }U\})
 \le e^{-c|U|}\mathbb P(E).
\]
This preserves the exterior-event probability with no division by that probability.

**Report:** [the density subsection](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:3227>) presents the unconditional gap, and later explains the loss under arbitrary rare pivotal conditioning. It does not state the narrower positive conditional result or its buffer hypotheses.

**Assessment:** partial coverage that misses an important distinction: this strengthening works for the specified distant-exterior events, while general pivotal normalization remains unresolved.

## Additional quantitative discoveries compressed out of the report

These supplement the main findings above.

| Source discovery | What the report retains | What is missing |
|---|---|---|
| [Complete outside-norm partition](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/pivotal_outside_norm_campbell.md:163>) | General variational limitations and the unknown weighted sign | The inequality \(I_F\le S_F\), the sufficient bound \(S_F\le c_0I_F+c_1J_F\) with \(c_1>0\), \(c_0+c_1<1\), and the distinction between a complete partition and fixed-cell eligibility |
| [Confluent multipair scalar mean](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/coalesced_multi_deletion_fock_mean.md:8>) and [explicit optimizer](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/multipair_fock_gram_optimization.md:86>) | Trial-space dimension, optimization-order warning, and the retained-arm limiting optimum | Exact polynomial moments and optimizer, Gaussian \(L^1\) convergence, and the unconditional finite-distinct-Palm outside-norm improvement with limit \(e^{-\pi b^2}<1\) |
| [Gaussian contact and dimer perimeter identities](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/research/current_law_contact_obstructions.md:75>) | Contact counterexamples and the dangerous predecessor | The half-Gaussian estimate for the deletion-stable part, the separate created-contact term, and the exact twin-contact/perimeter identity |
| [Higher-mark transport](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/multiple_omitted_marks_far_transport.md:266>) | The \(|z|^{-2k}\) tail and general selection warnings | Balanced-polygon tail improvements, the analytic inner-annulus lower bound, the determinant-retained sparse-polygon lower bound of order \(T^2/k\), and the exact correlated polygon projection formula |
| [Thinned-plus-Poisson Bennett theorem](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/thinned_ginibre_potential_bennett.md:1>) | The projection Bennett estimate and a source-map citation | The exact variance parameter \(V_*=s^2V_H+[s(1-s)+\nu]\int f^2\), its projection-dilation proof, and the additional \(L^{-6}\) potential variance term |
| [Fixed-count bridge motion](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/bridge_motion_continuation.md:7>) and [optimized rare-event rate](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/notes/ginibre_motion_independent_audit.md:49>) | Arbitrary-exterior likelihood obstruction and inverse moments \(q<1\) | The port-geometry support obstruction, exact conditional-expectation RN identity under thinning, and the latent-void comparison with optimized relative factor \(\exp[-(B+o(1))\log(1/p)/\log\log(1/p)]\) |

These are not all independent routes to the conjecture. Some sharpen an existing bound, some close a proposed shortcut, and some identify the precise quantity that remains uncontrolled. They are nevertheless discoveries recorded in the sources.

## Important material that is already covered

The audit should not be read as saying that the main report lost its principal conclusions.

| Result family | Report location |
|---|---|
| Optimal homogeneous Poisson domination and its lower critical-radius bound | [Core section 1](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:225>) |
| Signed Palm/Goldman interpolation, including thinning | [Core section 2](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:314>) |
| Fock variational identity and negative local multiplier | [Core section 3](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:373>) |
| Buffered Bergman domination and clustered-zero estimate | [Core section 4](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:427>) |
| Unbounded fixed-Palm exterior likelihood ratios | [Core section 5](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:475>) |
| Valid rank-two deletion and failed rank-three Lagrange rule | [Core section 6](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:568>) |
| Attached ellipse note’s large-area result, local Poisson convergence, actual threshold convergence, and joint thin-ellipse regime | [Ellipse section](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:607>) |
| Small-beta asymptotic, both the old and optimized remainder, geometric dependency, and endpoint argument | [Small-beta section](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:1532>) |
| Earlier void, cluster, contact, Coulomb, static-energy, and square-replacement routes | [Branch survey](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:2459>) |
| Saturated certificates, positive straight-ray family, circle motions, random Fock deficits, and rare-event losses | [Later branch survey](</home/benoit/Documents/Recherche/OpenMath/Radiuis comparison/ginibre_poisson_investigation_sources/ginibre_poisson_investigation.tex:3057>) |

The original comparison \(r_c(G)<r_c(\Pi_1)\) remains unresolved in both the source record and the report.

The small-beta result is **present, with a changed verification status**. The source notes call it proved/audited; the report explicitly makes it conditional on a fresh complete verification of the uniform geometric estimate. That is a status change, not an omission or a disproof. Assessing whether the downgrade is mathematically justified would require a separate proof audit.

## Suggested revision

Keep the present core and its verification distinctions. Add short propositions, recovered-result statements, or explicit counterexample summaries for the missing families above, with their exact scope and source references. The highest-priority additions are the quantitative ellipse results, the coupling barriers, the mixed-model threshold theorem, the clearing laws, and the bottleneck-switching obstruction.

A result-level source map would be more informative than the current filename-and-title index: each result should point to a report statement, or explicitly say “preserved only in the source archive,” with a reason if it is not adopted.

The accurate description of the current document is **a substantial but selective mathematical account accompanied by a complete preserved source archive**.

