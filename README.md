Despite the remarkable success of Graph Neural Networks (GNNs) in capturing complex relational dependencies, their inherent ``black-box'' nature poses significant challenges for high-stakes applications where transparency is non-negotiable. Existing interpretability methods often provide post-hoc explanations that lack causal rigor or fail to offer a corrective mechanism for erroneous reasoning. In this paper, we propose \textbf{G-XCSO}, a novel neuro-symbolic framework designed to bridge the gap between high-dimensional graph embeddings and human-understandable symbolic logic. Our approach integrates a GNN-based feature extractor with a Learning Classifier System (XCS) that serves as a symbolic oversight layer. By mapping continuous latent representations into a discrete symbolic space through a learned discretization function $\Phi$, G-XCSO distills complex graph topologies into actionable, if-then rules. We demonstrate through extensive experiments on MoleculeNet benchmarks that G-XCSO not only maintains competitive predictive accuracy but also provides a verifiable layer of interpretability, enabling the identification of adversarial subgraphs and ensuring adherence to predefined safety constraints.

keywords: Graph Neural Networks, Interpretability, Neuro-symbolic Learning, XCS, Symbolic Oversight, AI Alignment.

Introduction

The ability to learn meaningful representations from graph-structured data has revolutionized domains ranging from drug discovery to social network analysis. Graph Neural Networks (GNNs) have emerged as the state-of-the-art paradigm for these tasks, leveraging message-passing mechanisms to aggregate neighborhood information. However, as these models grow in depth and complexity, they increasingly suffer from a fundamental flaw: the \textit{interpretability crisis}.

The decision-making process of a GNN occurs within a high-dimensional, continuous latent space that is virtually opaque to human experts. While post-hoc explanation techniques (e.g., GNNExplainer) attempt to highlight influential subgraphs, they often fail to explain \textit{why} a specific structural pattern leads to a certain prediction, nor can they provide a formal guarantee that the model's reasoning aligns with domain-specific logic. In critical fields such as pharmacology, an incorrect prediction caused by a spurious correlation in the graph topology can lead to catastrophic real-world consequences.

To address this, we argue that interpretability should not be an afterthought but an intrinsic component of the architectural design. We propose a shift from purely connectionist models to a \textbf{Neuro-symbolic Oversight} paradigm. We introduce \textbf{G-XCSO}, a framework that marries the perceptual power of GNNs with the transparent reasoning of Learning Classifier Systems (XCS). 

The core intuition behind G-XCSO is to treat the GNN as an "encoder" that perceives the graph, while the XCS acts as a "symbolic supervisor" that interprets these perceptions. Our key contributions are as follows:

    Integrated Neuro-Symbolic Architecture: We design a novel architecture where a GNN's continuous embeddings are transformed via a discretization function $\Phi$ into a symbolic state space, allowing XCS to evolve a population of human-readable rules.
    
    Symbolic Oversight Mechanism: Unlike standard interpretability methods, our framework provides an active oversight layer that can detect and penalize reasoning that deviates from symbolic safety constraints.
    
    Empirical Validation of Interpretability: We provide evidence that G-XCSO effectively distills complex graph features into "If-Then" rules, significantly reducing the opacity of graph-based decision-making without compromising predictive performance.
