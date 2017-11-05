slidenumbers: true
build-lists: true
footer: UCLA Vision, Cognition, Learning, and Autonomy Lab (VCLA)

# Learning Human Utility from Video Demonstrations for Deductive Planning in Robotics

### Nishant Shukla, Yunzhong He, Frank Chen, & Song-Chun Zhu

---

# Model

---

# Definition 1. Environment

- The world (or _environment_) is defined by the stochastic context-free And-Or graph (AOG).
- AOG explicity models variations and compositions of spatial ($$S$$), temporal ($$T$$), and causal ($$C$$) concepts, called the STC-AOG.

---

# Definition 1. Environment (_continued_)

- The atomic (_terminal_) units of this grammar are tuples of the form $$(F_{start}, u_{[1:t]}, F_{end})$$

- $$F_{start}$$ and $$F_{end}$$ are pre- and post- fluents of a sequence of interactions $$u_{[1:t]}$$.
- $$u_{[1:t]}$$ is implemented by spatial and temporal features of human-object interactions.

---

# Definition 2. State

- A _state_ is a configuration of the believed model of the world. 
- We use a parse-graph ($$pg$$) of the And-Or graph, representing a selection of parameters ($$\Theta_{OR}$$) for each Or-node.
- The set of all parse-graphs is denoted $$\Omega_{pg}$$.

---

# Definition 3. Fluent

- A _fluent_ is a condition of a state that can change over time. 
- It is represented as a real-valued function on the state (indexed by $$i \in \mathbb{N}$$): $$f_i : \Omega_{pg} \rightarrow \mathbb{R}$$ 

---

# Definition 4. Fluent-vector

- A _fluent-vector_ $$F$$ is a column-vector of fluents: $$F = (f_1, f_2, ..., f_k)^T$$.

---

# Definition 5. Goal

- The _goal_ of a task is characterized by a fluent-change $$\Delta F$$. 
- The purpose of learning the utility function is to identify reasonable goals.

---

# The Utility Model

- We assume human preferences are derived from a utilitarian model: a latent utility function assigns a real-number to each configurations of the world.

---

# The Utility Model: an example

- Each video demonstration contains a sequence of $$n$$ states $$pg^0$$, $$pg^1$$, ..., $$pg^n$$, which offers $$n(n-1)/2$$ possible ordered pairs (**ranking constraints**).
- If state $$pg^1$$ has a higher utility than another state $$pg^2$$, then ranking is denoted $$pg^1 \succ pg^2$$. 
- Given the ranking constraints, we define an energy function by how consistent a utility function is with the constraints.