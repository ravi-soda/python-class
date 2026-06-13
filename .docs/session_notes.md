------ 
learn mantras of each topic (Embeddings, word2vec: depends on neighbout word)
learn where each concept fails (polysemy)
learn the parameters is a function of what and what
------


Sigmoid: Like a probability meter, giving values between 0 and 1.
Tanh: Like a sentiment scale, giving values between −1 (negative) and +1 (positive).
ReLU: Like an on/off switch—negative values become 0, positive values pass through.
Tanh is often preferred in RNNs because it can represent both positive and negative information, making it easier to model context and memory.


Yess, somewhat for long-term dependencies

RNN + BPTT can lead to vanishing and exploding gradient problems when learning long-term dependencies.


Yes. The current hidden state is computed using the current input, the previous hidden state (memory), and some learnable weights and biases, followed by an activation function such as tanh. This allows the RNN to carry information from earlier time steps and use it when processing new inputs.


So we are sudying the RNN concept where the motivation is to analyze sequential data like text/audio. So we need to analyze the embeddings of the current input along with the representations of the previous inputs right? So here is where the Back prop over Time of RNN comes in 


Vanishing and exploding gradients are fundamentally training problems. Vanishing gradients indirectly cause memory issues because the network struggles to learn and retain long-range dependencies.

<img width="933" height="539" alt="image" src="https://github.com/user-attachments/assets/02ac17de-e49b-4539-a7e0-61852a463f95" />

What exactly prevents the hidden state in a Vanilla RNN from retaining information over thousands of timesteps????


Abdeali Dodiya 09:22 AM 
is vanishing gradient fundamentally training problem , memory problem or both??
Academic_Lead_SB 09:24 AM 
Vanishing gradient is fundamentally a training problem because the gradients become extremely small during backpropagation, making it difficult to update parameters associated with earlier time steps. However, it also leads to a memory problem in RNNs, since the model struggles to learn long-range dependencies and effectively "forgets" information from the distant past. So, it originates as a training issue but manifests as poor long-term memory.





