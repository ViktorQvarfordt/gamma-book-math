
# Language models and their perceptible spectra of reality

*Archipelagic perspectives on mathematics, physics and perceptible spectra of reality*

*Viktor Qvarfordt, 2021-09-02*

----

In this talk I will give an introduction to state of the art language models. We will see how language models are trained and demonstrate their ability to perform meta-learning. The success is based on the fact that neural networks continue to scale with increased performance as three parameters grow: The number of model parameters, the size of the training data and the amount of compute.

----


## Background

- This will be a slightly different presentation
- Overview of the core parts of the theory
- Develop intuition by interacting with the model

<!--
I'm no longer actively working with mathematics or physics but programming and working closely with AI systems. The purpose of this session is to share with you the most impactful and interesting updates from the field.

Rather than purely focusing on theory, we will get hands-on experience to develop some intuition and to spur further discussion and conversation in the intersection of mathematics, physics and perceptible spectra of reality.
-->

## Agenda

- Definition of a language model
- Meta learning and few shot learning
- State of the art language models: GPT-3
- Examples
- Discussion

## Why is this interesting?

Language models are general AI models that can solve task in multiple domains without having to be re-trained. Building on the idea that language encodes most of what is interesting.

This class of models can be seen as a significant step in the direction of AGI. The possible applications are vast and we are just getting started.

Neural-network based model continue to scale exceptionally well. This is somewhat surprising.

<img src="https://www.gwern.net/images/ai/gpt/2019-11-07-amodei-aiandcompute-twodistincteras-gpt3modified.png" style="max-width: 100%; padding: 1rem;" />

<img src="https://www.gwern.net/images/ai/gpt/2020-kaplan-figure1-dlscaling.png" style="max-width: 100%; padding: 1rem;" />

### Meta learning

What is meta-learning? A model that has "learned how to learn".

Without re-training the model on new data, the model can perform different tasks.


## Definition of a language model

A statistical language model is a probability distribution over sequences of words. Given such a sequence, say of length $m$, it assigns a probability $P(w_{1},\ldots ,w_{m})$ to the whole sequence.

Typically, neural net language models are constructed and trained as probabilistic classifiers that learn to predict a probability distribution

### Training a language model

A language model is trained by having it predict small parts of large amounts of unlabeled text.

I.e., the network is trained to predict a probability distribution over the vocabulary, given some linguistic context.

$$
P(w_{t}\mid \mathrm {context} )\,\forall t\in V
$$

This is done using standard neural net training algorithms such as stochastic gradient descent with backpropagation.​ The context might be a fixed-size window of previous words, so that the network predicts

$$
P(w_{t}\mid w_{t-k},\dots ,w_{t-1})
$$

from a feature vector representing the previous k words.

Another option is to use "future" words as well as "past" words as features, so that the estimated probability is

$$
P(w_{t}\mid w_{t-k},\dots ,w_{t-1},w_{t+1},\dots ,w_{t+k}).
$$

In practice this gives the model a very robust context awareness.

### Training a neural network

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/60/ArtificialNeuronModel_english.png/800px-ArtificialNeuronModel_english.png" style="max-width: 100%; padding: 1rem;" />


$$
\begin{aligned}
{\frac {\partial E}{\partial w_{ij}}} &= {\frac {\partial E}{\partial o_{j}}}{\frac {\partial o_{j}}{\partial w_{ij}}}={\frac {\partial E}{\partial o_{j}}}{\frac {\partial o_{j}}{\partial {\text{net}}_{j}}}{\frac {\partial {\text{net}}_{j}}{\partial w_{ij}}} \\

{\frac {\partial {\text{net}}_{j}}{\partial w_{ij}}} &= {\frac {\partial }{\partial w_{ij}}}\left(\sum _{k=1}^{n}w_{kj}o_{k}\right)={\frac {\partial }{\partial w_{ij}}}w_{ij}o_{i}=o_{i}. \\

{\frac {\partial o_{j}}{\partial {\text{net}}_{j}}} &= {\frac {\partial }{\partial {\text{net}}_{j}}}\varphi ({\text{net}}_{j})=\varphi ({\text{net}}_{j})(1-\varphi ({\text{net}}_{j}))=o_{j}(1-o_{j}) \\

\frac{\partial E}{\partial o_j} &= \frac{\partial E}{\partial y} = \frac{\partial}{\partial y} \frac{1}{2}(t - y)^2 = y - t \\

{\frac {\partial E}{\partial o_{j}}} &= \sum _{\ell \in L}\left({\frac {\partial E}{\partial {\text{net}}_{\ell }}}{\frac {\partial {\text{net}}_{\ell }}{\partial o_{j}}}\right)=\sum _{\ell \in L}\left({\frac {\partial E}{\partial o_{\ell }}}{\frac {\partial o_{\ell }}{\partial {\text{net}}_{\ell }}}{\frac {\partial {\text{net}}_{\ell }}{\partial o_{j}}}\right)=\sum _{\ell \in L}\left({\frac {\partial E}{\partial o_{\ell }}}{\frac {\partial o_{\ell }}{\partial {\text{net}}_{\ell }}}w_{j\ell }\right)

\end{aligned}
$$

## GPT3

GPT3 is a language model created by Open AI. At its core, GPT-3 is basically a transformer model - a type of neural network model.

GPT-3 is trained on an unlabeled text dataset (a large chunk of the internet): Words or phrases are randomly removed from the text, and the model must learn to fill them in using only the surrounding words as context. It’s a simple training task that results in a powerful and generalizable model.

- 175 billion (~$10^{11}$) parameters
- Trained on ~trillion ($10^{12}$) words
- $4.6 million just for the hardware cost to train the model. Plus cost for research and engineering.

### Transformer model

A transformer is a deep learning model that adopts the mechanism of attention, differentially weighing the significance of each part of the input data. It is used primarily in the field of natural language processing (NLP) and in computer vision (CV).

Like recurrent neural networks (RNNs), transformers, are designed to handle sequential input data. However, unlike RNNs, transformers do not necessarily process the data in order. Rather, the attention mechanism provides context for any position in the input sequence. For example, if the input data is a natural language sentence, the transformer does not need to process the beginning of the sentence before the end. Rather, it identifies the context that confers meaning to each word in the sentence. This feature allows for more parallelization than RNNs and therefore reduces training times.


### Interacting with the model

- Text in. Text out.
- The model continues the input text with the text that is "the most likely" given the context.

One does not train or program GPT-3 in a normal way, but one engages in dialogue and writes prompts to teach GPT-3 what one wants.

In this way, unlocking remarkable flexibility in the form of meta-learning, where GPT-3 can infer new patterns or tasks and follow instructions purely from text fed into it.

This is considered “meta-learning” because GPT-3 has “learned how to learn”: in its endless training on so many gigabytes of text, it encounters so many different kinds of text that it had no choice but to learn abstractions & how to understand descriptions & instructions & formatting & authorial intent to let it adapt on the fly to the current piece of text it was training on, since there was too much diversity & data for it to simply learn each task normally by repeated exposure—much less memorize all the data.

#### Programming by dialogue

Program the model by describing what you want in natural text.

If a human had already written out what I wanted, what would the first few sentences sound like? What would the introduction and summary sound like?

<img src="https://www.gwern.net/images/ai/gpt/2020-06-18-karpathy-expandingbrainmeme-gpt3metalearning.jpg" style="max-width: 100%; padding: 1rem;" />


## Examples

- https://beta.openai.com/examples
- https://openai.com/blog/openai-codex


## Discussion

- What are the limits of of this approach?
- Are humans basically such generative statistical models?
- How will this impact the future of how we do science and mathematics?
- Currently the model is not good on math. Why is that? Small data set. Math has a somewhat different structure than natural language.
- Can such systems become conscious? “I am open to the idea that a worm with 302 neurons is conscious, so I am open to the idea that GPT-3 with 175 billion parameters is conscious too.” — David Chalmers
