# turkish-lstm-language-model
Experimental LSTM-based language modeling project on Turkish literary prose, using bag-of-characters encoding and public-domain texts.


### Experimental Setup
The model was trained on public-domain short stories by Ömer Seyfettin collected from Wikipedia.
A bag-of-characters encoding was used as input representation, allowing the model to capture
character-level distributions without explicit tokenization.

Two different architectures were evaluated:
- 1-layer LSTM
- 2-layer LSTM

Both models were trained under identical conditions to compare representation capacity
and overfitting behavior.


### Qualitative Results
Given the same prompt, the behavior of the two architectures differs significantly.

- **1-layer LSTM** tends to reproduce large portions of the training text, indicating
  strong memorization and overfitting.
- **2-layer LSTM** generates novel text that preserves the author's stylistic patterns
  while avoiding direct copying.

This suggests that deeper recurrent representations increase abstraction capacity,
making exact memorization more difficult while still retaining stylistic cues.



### Training Dynamics
A rapid decrease in loss was observed during early training stages.
This indicates that the model quickly captures low-level statistical regularities,
primarily grammatical and syntactic patterns.

As training progresses, further loss reduction becomes increasingly difficult.
At this stage, the model is forced to learn higher-level semantic dependencies,
which are inherently harder to model with standard LSTM architectures.

This behavior was consistent across experiments and highlights the transition from
surface-level pattern learning to deeper semantic representation.


### Model Comparison
- The **1-layer LSTM** exhibits strong overfitting behavior by partially copying training samples.
- The **2-layer LSTM** demonstrates improved generalization by learning more abstract
  representations of style rather than exact sequences.

The increased representational complexity of the deeper model acts as an implicit
regularizer, making direct memorization more difficult.


### Limitations
- The model maintains coherence primarily at the sentence level.
- Long-range narrative structure and plot consistency are not preserved.
- These limitations are expected due to the restricted memory capacity
  of vanilla LSTM architectures.


### Key Takeaway
This project demonstrates how LSTM-based language models transition from learning
syntactic regularities to attempting semantic structure, and how increased depth
affects memorization and generalization trade-offs in literary text modeling.
