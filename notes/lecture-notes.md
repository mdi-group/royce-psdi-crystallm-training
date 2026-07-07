
# Slide 1 — Introduction to LLMs

- Today we'll build up to Large Language Models from first principles.
- The key idea is not language itself, but representation learning.
- We'll start with classical machine learning and see what's different about deep learning.
- Then we'll look at how words can be represented numerically.
- This naturally leads to neural networks, sequence models and finally transformers.

---

# Slide 2 — Classical vs Deep Methods

- Both classical ML and deep learning learn relationships from data.
- Classical methods often rely on carefully designed input features.
- Deep learning uses neural networks to learn useful features automatically.
- The important distinction is not simply "more layers".
- The real breakthrough is learning representations directly from data.

---

# Slide 3 — Deep Learning as Representation Learning

- Traditional ML separates feature extraction from prediction.
- Success often depends on choosing the right features beforehand.
- This becomes difficult for images, text and other unstructured data.
- Deep learning learns intermediate representations automatically.
- We can think of the network as learning a transformation of the input before making predictions.

---

# Slide 4 — Example: Cat vs Snake

- In a classical approach we explicitly define properties such as scales, whiskers or number of legs.
- This requires prior knowledge of what matters.
- A deep network starts from raw pixels alone.
- Early layers learn simple patterns; later layers combine them into more abstract concepts.
- The representation itself becomes part of the learning problem.

**Question for the audience:** *What should a representation actually look like?*

---

# Slide 5 — Localised or Distributed Representations?

**TRANSITION: We've established that deep learning is about learning representations. The next question is: what should a representation actually look like?**

- Once we accept representation learning, we need to decide how to represent concepts.
- A localist representation uses one dimension per concept ("one-hot" style).
- These are easy to interpret but carry little information about similarity.
- Distributed representations spread information across many dimensions.
- Similar concepts end up with similar representations, making generalisation possible.

---

# Slide 6 — Learning Distributed Representations

- How can a model discover useful word representations automatically?
- Firth's famous idea: "You know a word by the company it keeps."
- Words appearing in similar contexts tend to have related meanings.
- Even an unknown word can be understood from surrounding words.
- The objective becomes learning representations that capture contextual information.

**Question for the audience:** *How do we actually learn such a representation?*

---

# Slide 7 — Multi-Layer Perceptrons

**TRANSITION: We now know that distributed representations are desirable and can be learned from context. The next question is how a machine can actually learn them.**

- To learn representations we need a trainable model.
- The simplest deep neural network is the multi-layer perceptron.
- Layers progressively transform one representation into another.
- Hidden layers allow the model to learn increasingly abstract features.
- This architecture forms the foundation of many later neural network designs.

---

# Slide 8 — Dense Layers

- Each neuron computes a weighted combination of its inputs.
- The weights determine what information is important.
- The activation function introduces non-linearity.
- Without non-linearities, multiple layers would collapse into a single linear model.
- Learning means adjusting the weights and biases to improve predictions.

---

# Slide 9 — Backpropagation

- The question now is: how do we adjust millions of parameters efficiently?
- Backpropagation computes how much each parameter contributed to the error.
- It uses the chain rule to propagate information backward through the network.
- Gradients tell us how to update each parameter to reduce the loss.
- Modern frameworks automate this, but it's the engine behind deep learning.

**Question for the audience:** *What useful representations can we learn with this machinery?*

---

# Slide 10 — Learning Word Embeddings

**TRANSITION: Backpropagation tells us how neural networks learn. Now let's apply it to our original problem—learning representations of words.**

- We can use an MLP to learn word representations from context prediction.
- A common approach is skip-gram: predict surrounding words from a target word.
- The network is trained over huge text corpora.
- During training, useful word embeddings emerge in the hidden layers.
- The learned embeddings become our distributed representation of words.

**Question for the audience:** *What is still missing if we want to model language?*

---

# Slide 11 — Sequence Data

**TRANSITION: Word embeddings solve the representation problem for individual words. But language is more than isolated words—it is fundamentally sequential.**

- So far we've ignored an important property of language: order matters.
- MLPs assume fixed-size inputs and outputs.
- Language sequences vary in length and depend on context.
- We therefore need architectures designed specifically for sequential information.
- This motivates recurrent neural networks.

---

# Slide 12 — Recurrent Neural Networks

- RNNs introduce the concept of a hidden state.
- The hidden state acts as a memory of previous inputs.
- Information is processed token by token.
- The same parameters are reused at every step.
- In principle this allows arbitrarily long sequences to be modelled.

---

# Slide 13 — Issues with RNNs

- In practice RNNs struggle to retain information over long distances.
- Recent words tend to dominate the hidden state.
- Important context can be forgotten as sequences grow longer.
- This makes long-range reasoning difficult.
- The search for better long-term memory led to attention mechanisms and transformers.

**Question for the audience:** *How can we model long-range context without forgetting it?*

---

# Slide 14 — Transformers

**TRANSITION: RNNs gave us sequence modelling, but their limited memory means they struggle with long-range dependencies. We need a different mechanism for handling context.**

- Transformers abandon purely sequential processing.
- All tokens can interact in parallel.
- This makes training dramatically more efficient.
- Instead of relying on hidden-state memory, transformers explicitly model relationships between tokens.
- The unit being processed is a token, not necessarily a complete word.

---

# Slide 15 — The Attention Mechanism

- Attention answers the question: which pieces of information are relevant right now?
- Different tokens contribute differently to understanding a sentence.
- Attention assigns a weight to each relationship.
- Important tokens receive larger weights.
- This allows the model to dynamically focus on relevant context.

---

# Slide 16 — Self-Attention

- Self-attention lets tokens interact with other tokens in the same sequence.
- Each token builds a context-aware representation of itself.
- The meaning of a word depends on surrounding words.
- This resolves many ambiguities that static embeddings cannot handle.
- Context is no longer compressed into a single memory state.

---

# Slide 17 — How Self-Attention Works

- Self-attention is built around queries, keys and values.
- Queries ask: "What am I looking for?"
- Keys describe what information each token contains.
- Matching queries to keys determines relevance.
- Values contain the information that is ultimately exchanged.

---

# Slide 18 — Attention Inputs

- Every token begins as an embedding vector.
- Learned projections create query and key representations.
- Query-key similarity determines which tokens should interact.
- These projections are learned entirely from data.
- The model discovers useful linguistic relationships automatically.

---

# Slide 19 — Query-Key Multiplication

- Multiplying queries and keys produces attention scores.
- Large scores indicate strong relevance between tokens.
- Softmax converts these scores into probabilities.
- The resulting matrix describes who attends to whom.
- This is the core operation responsible for contextual reasoning.

---

# Slide 20 — The Value Matrix

- Values hold the information that will actually be transferred.
- Attention scores determine how much of each value is used.
- Relevant words contribute more strongly.
- Irrelevant words contribute very little.
- Context is injected directly into token representations.

---

# Slide 21 — Adding Values to Embeddings

- The weighted value vectors are combined with the original embeddings.
- Each token representation becomes context-aware.
- The same word can therefore have different embeddings in different sentences.
- This is a major advantage over static word embeddings.
- Meaning becomes dependent on context.

---

# Slide 22 — Updating Embeddings / Multi-Head Attention

- The attention operation produces updated embeddings.
- Different attention heads can specialise in different relationships.
- Some heads track syntax, others long-range dependencies or semantic meaning.
- Combining multiple heads enriches the representation.
- This mechanism is one of the reasons transformers are so powerful.

**Question for the audience:** *Why should we care about all of this in a scientific context?*

---

# Slide 23 — CrystaLLM

**TRANSITION: We've now covered how transformers work. The final step is to see how the same architecture can be applied beyond natural language to scientific data.**

- Everything we've discussed so far applies beyond natural language.
- CIF files can also be treated as token sequences.
- CrystaLLM is a decoder-only transformer trained on crystal structures.
- The model learns statistical patterns in known materials.
- This allows it to generate plausible new structures.

---

# Slide 24 — Autoregressive Generation

- During generation, the model predicts one token at a time.
- Each new prediction becomes part of the context for the next step.
- The process continues until a complete structure is produced.
- Prompting allows us to control the information supplied to the model.
- This is the same principle used in modern chat-based LLMs.

---

# Slide 25 — Monte Carlo Tree Search for Consistency

- Pure autoregressive generation does not guarantee physically meaningful structures.
- Some generated sequences correspond to unrealistic materials.
- Monte Carlo Tree Search explores multiple possibilities.
- An energy model guides the search toward lower-energy candidates.
- This shows how domain knowledge can be combined with generative AI.

