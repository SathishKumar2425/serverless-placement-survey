# Serverless Function Placement across Edge-Cloud: A Living Survey

A structured, living literature review of **optimization techniques for placing
serverless functions across edge-cloud infrastructure**: taxonomy, comparison
tables, and a curated reference list. The review scope and research questions
below are stated verbatim by the author; everything else in this repository is
organized to answer them.

## Review scope

This review examines **optimization techniques for placing serverless functions across edge–cloud infrastructure**. It focuses on how methods decide where functions, workflow steps, or invocations should run, and how they balance performance, cost, and resource constraints.

The review covers four main method families: exact mathematical or constraint-based optimization; structured search, heuristics, and dynamic programming; evolutionary and other multi-objective methods; and machine-learning or reinforcement-learning approaches. It considers factors such as latency, execution cost, node capacity, workflow dependencies, deadlines or service-level objectives (SLOs), cold starts, package or layer reuse, and network conditions.

To keep the comparison meaningful, the review distinguishes **direct FaaS placement** from adjacent problems. Invocation scheduling within a cluster, workflow resource configuration, generic application or service placement, and edge-cloud task offloading are included only as related evidence and are not treated as equivalent to choosing an execution location for serverless functions.

The review compares the methods’ decision models, objectives, constraints, strengths, limitations, and evaluation practices. It does not propose a new placement algorithm, conduct a new experiment, or claim a systematic, exhaustive search of all publications. Results reported by different papers are treated as study-specific because their workloads, metrics, baselines, and test environments differ.

## Research questions

**RQ1.** What optimization method families have been used to place serverless functions across edge–cloud environments, and how do their decision processes differ?

**RQ2.** What objectives and constraints do these methods model, including latency, monetary cost, resource capacity, workflow dependencies, deadlines or SLOs, cold starts, package reuse, and network conditions?

**RQ3.** What are the comparative strengths and limitations of exact optimization, heuristics and structured search, evolutionary methods, and learning-based approaches, particularly regarding solution quality, scalability, adaptability, and decision overhead?

**RQ4.** How are proposed placement methods evaluated, and what workloads, baselines, metrics, simulations, prototypes, or testbeds are used?

**RQ5.** What gaps limit fair comparison and practical deployment, and which research directions could improve realistic, reproducible, and network-aware serverless placement?

## Taxonomy of placement methods

| Family | Decision model | Typical strengths | Typical limitations | Seeded papers |
|---|---|---|---|---|
| **F1. Exact / constraint-based optimization** (ILP, INLP, CP) | Formulate placement as a mathematical program; a solver returns the provably optimal placement for the stated model | Optimality guarantees; explicit constraints | Solver time grows with problem size; model must be re-solved on change | 2 papers (see References) |
| **F2. Heuristics, structured search, dynamic programming** | Domain-specific rules, greedy or bounded search, DP recurrences over workflow structure | Fast, predictable decision overhead; easy to deploy | No optimality guarantee; quality depends on heuristic design | 2 papers (see References) |
| **F3. Evolutionary / multi-objective methods** (GA, Pareto-front search) | Evolve a population of placements toward a Pareto front over conflicting objectives | Handles multiple objectives explicitly; no gradients needed | Many evaluations per decision; convergence tuning | 2 adjacent-problem papers (related evidence); direct-FaaS papers *to be added* |
| **F4. Learning-based (ML / RL)** | Learn a placement policy or value function from experience; adapt online | Adapts to changing conditions; no hand-crafted model | Training cost and stability; sim-to-real gap; sample efficiency | 3 papers (see References) |

## Comparison tables (skeletons)

Tables are seeded with verified papers only; empty cells are marked
*TBA (to be added)* as the review progresses.

### RQ1: method families and decision processes

| Paper | Family | When decided (offline / online / hybrid) | Decision inputs | Granularity (function / workflow step / invocation) |
|---|---|---|---|---|
| Performance Optimization for Edge-Cloud Serverless Platforms via Dynamic Task Placement (2020) | F1 | *TBA* | *TBA* | *TBA* |
| Large-scale workflow placement in serverless computing using integer nonlinear programming (2026) | F1 | *TBA* | *TBA* | *TBA* |
| Efficient and Dependency-Aware Placement of Serverless Functions on Edge Infrastructures (2024) | F2 | *TBA* | *TBA* | *TBA* |
| Latency-Sensitive Function Placement among Heterogeneous Nodes in Serverless Computing (2024) | F2 | *TBA* | *TBA* | *TBA* |
| Optimizing Service Placement in Edge-to-Cloud AR/VR Systems using a Multi-Objective Genetic Algorithm (2024) *(adjacent: service placement)* | F3 | *TBA* | *TBA* | *TBA* |
| Investigating Pareto front multi-objective optimization for edge computing service placement (2026) *(adjacent: service placement)* | F3 | *TBA* | *TBA* | *TBA* |
| POSEIDON: Efficient Function Placement at the Edge using Deep Reinforcement Learning (2024) | F4 | *TBA* | *TBA* | *TBA* |
| FoRLess: A Deep Reinforcement Learning-based approach for FaaS Placement in Fog (2024) | F4 | *TBA* | *TBA* | *TBA* |
| Configuration and Placement of Serverless Applications Using Statistical Learning (2023) | F4 | *TBA* | *TBA* | *TBA* |

### RQ2: objectives and constraints modeled

| Paper | Latency | Monetary cost | Node capacity | Workflow dependencies | Deadlines / SLOs | Cold starts | Package / layer reuse | Network conditions |
|---|---|---|---|---|---|---|---|---|
| *(one row per paper, filled as each paper is reviewed)* | | | | | | | | |

### RQ3: strengths and limitations by family

| Family | Solution quality | Scalability | Adaptability | Decision overhead | Evidence (papers) |
|---|---|---|---|---|---|
| F1. Exact / constraint-based | *TBA* | *TBA* | *TBA* | *TBA* | *TBA* |
| F2. Heuristics / structured search / DP | *TBA* | *TBA* | *TBA* | *TBA* | *TBA* |
| F3. Evolutionary / multi-objective | *TBA* | *TBA* | *TBA* | *TBA* | *TBA* |
| F4. Learning-based (ML / RL) | *TBA* | *TBA* | *TBA* | *TBA* | *TBA* |

### RQ4: evaluation practices

| Paper | Workloads | Baselines compared | Metrics | Simulator / prototype / testbed |
|---|---|---|---|---|
| *(one row per paper)* | | | | |

### RQ5: gaps and research directions

| # | Gap or direction | Evidence (papers affected) | Status |
|---|---|---|---|
| 1 | *To be added as the review progresses* | | |

## References

Verified entries only: each was checked by title, venue, year, and link before
inclusion. Papers on adjacent problems (generic service placement, offloading)
are marked *(adjacent)* and count as related evidence per the review scope.

**F1. Exact / constraint-based optimization**

1. Performance Optimization for Edge-Cloud Serverless Platforms via Dynamic Task Placement. *IEEE/ACM CCGrid*, 2020. https://doi.org/10.1109/ccgrid49817.2020.00-89
2. Large-scale workflow placement in serverless computing using integer nonlinear programming. *arXiv:2608.14427*, 2026. https://arxiv.org/abs/2608.14427

**F2. Heuristics, structured search, dynamic programming**

3. Efficient and Dependency-Aware Placement of Serverless Functions on Edge Infrastructures. *Service-Oriented Computing (ICSOC), Springer LNCS*, 2024. https://dl.acm.org/doi/abs/10.1007/978-981-96-0805-8_1
4. Latency-Sensitive Function Placement among Heterogeneous Nodes in Serverless Computing. 2024. https://pmc.ncbi.nlm.nih.gov/articles/PMC11243899/

**F3. Evolutionary / multi-objective methods**

5. Optimizing Service Placement in Edge-to-Cloud AR/VR Systems using a Multi-Objective Genetic Algorithm. *arXiv:2403.12849*, 2024. https://arxiv.org/abs/2403.12849 *(adjacent)*
6. Investigating Pareto front multi-objective optimization for edge computing service placement. *Computer Networks*, 2026. https://doi.org/10.1016/j.comnet.2026.112213 *(adjacent)*
7. *Direct-FaaS evolutionary placement papers: to be added.*

**F4. Learning-based (ML / RL)**

8. POSEIDON: Efficient Function Placement at the Edge using Deep Reinforcement Learning. *arXiv:2410.11879*, 2024. https://arxiv.org/abs/2410.11879
9. FoRLess: A Deep Reinforcement Learning-based approach for FaaS Placement in Fog. *IEEE/ACM UCC*, 2024. https://dl.acm.org/doi/10.1109/UCC63386.2024.00026
10. Configuration and Placement of Serverless Applications Using Statistical Learning. *IEEE Transactions on Network and Service Management (TNSM)*, 2023. https://doi.org/10.1109/tnsm.2023.3254437

**Related surveys and reviews**

11. A survey on the scheduling mechanisms in serverless computing: a taxonomy, challenges, and trends. *Cluster Computing*, 2024. https://dl.acm.org/doi/10.1007/s10586-023-04264-8
12. Serverless Edge Computing: A Taxonomy, Systematic Literature Review, Current Trends and Research Challenges. *arXiv:2502.15775*, 2025. https://arxiv.org/html/2502.15775

## Conventions

- New papers are added only after verifying title, venue, year, and a working
  link. Unverified leads go in a "to be added" note, never in References.
- Results quoted from a paper stay study-specific: workloads, metrics,
  baselines, and test environments differ across papers, so no cross-paper
  performance ranking without a shared evaluation setting.

