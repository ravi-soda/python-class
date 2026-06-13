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

At what point do we decide whether we will do a back prop or forward feed ? 
Acamdemic_Leads_SM 10:07 AM 
Forward pass is used to make a prediction. Backpropagation is used during training, after computing the prediction error, to update the model's weights. During inference, only the forward pass is used.


Varadarajan Krishnan 10:07 AM 
The bank in another sentence could mean very similar in reference to each other. So will that also have a different vector

I went to the bank today

The bank is closed today

How will these two be handled?
Acamdemic_Leads_SM 10:09 AM 
In Word2Vec/GloVe, "bank" will have the same vector in both sentences. In BERT-like models, it will have slightly different vectors because the surrounding context is different, but the vectors will still be very similar since the meaning is the same.


Vamsi Krishna Akhil Jonnalagadda 10:08 AM 
Word2Vec always preferable or are there any use cases for Word2Vec and ELMO?
Acamdemic_Leads_SM 10:10 AM 
Word2Vec is faster and simpler, so it is useful when context is less important. ELMo understands context, so the same word can have different meanings in different sentences. Use Word2Vec for efficiency and ELMo for better contextual understanding.


Vishal Pardeshi 09:04 AM  
Sir Can you please make it full screen
Academic_Lead_SB 09:04 AM 
it is visible in full screen, kindly check from your end once
Vishal Pardeshi 09:05 AM  
sir's video is not movable on top
Moderator – VM would like to answer this question live.
Anonymous attendee 09:07 AM  
what is Vanilla RNN?
Chandan Kumar_TA 09:09 AM 
the most basic RNN is being explained
Rama Subba Reddy  Yarramachu 09:08 AM  
what is hidden state in RNN?
Chandan Kumar_TA 09:09 AM 
the most basic RNN is being explained by professor
Anonymous attendee 09:08 AM  
is it a basic RNN with minimum configurations?
Academic_Lead_SB 09:08 AM 
yes
Adrish Ray 09:09 AM  
We have missed few topics(like tokenisation etc) last week, any idea when those will be covered?
Academic_Lead_SB 09:09 AM 
The text pre-processing part will come in the tutorials
Bandna Uppal 09:10 AM  
How the ht determined at first step

Chandan Kumar_TA 09:13 AM 
In RNN, at the very first time step there is no previous hidden state.
We initialize h_0 as a vector of zeros.
Then we calculate h_1 using the first input x_1 and this zero vector

Vinayak Manwatkar 09:10 AM  
Could you please explain hidden state again please?
Acamdemic_Leads_SM 09:12 AM 
The internal memory of an RNN/LSTM that stores information from previous inputs and passes it to the next time step.
Dev Kumar 09:11 AM  
What is time step wrt to RNN?
Academic_Lead_SB 09:16 AM 
In an RNN, a time step refers to a single position in a sequence where the network processes one input element.
Mahesh Sawant 09:11 AM  
What is o/p computation function g()?
Academic_Lead_SB 09:17 AM 
activation function...... tanh
Vikram Vangala 09:11 AM  
WHy only Tanh ( I mean why not Sin or Cos ), Is that a standard function for the update rule ?
Vishnuvardhan_TA 09:16 AM 
RNNs multiply the exact same weights at every time step. Tanh keeps outputs between -1 and 1, which keeps the hidden state stable and prevents the values from exploding to infinity.

But with Sin/Cos, They are periodic (they wave up and down infinitely). This creates a chaotic loss landscape with infinite local minima, making it a nightmare for gradient descent to learn a clear path to zero error.
Acamdemic_Leads_SM 09:16 AM 
tanh is commonly used in RNNs because it is non-linear, smooth, differentiable, zero-centered, and bounded between -1 and 1, which helps keep hidden states stable during training. Functions like sin or cos can also be used, but their periodic nature means very different inputs can produce the same output, making it harder for the network to learn and maintain meaningful memory. For these reasons, tanh became the standard activation function for hidden state updates in classical RNNs, LSTMs, and GRUs.
Jasleen Kaur 09:14 AM  
hidden layer is also a learnable weight?
Chandan Kumar_TA 09:17 AM 
Kind of Yes.
The hidden layer itself is not a weight. It is a layer of neurons.
But the connections (weights and biases) between layers are learnable parameters.
Ananya Pandey 09:14 AM  
if we are carrying the hidden state , then why is back propagation needed ?
Academic_Lead_SB 09:17 AM 
back prop is required to learn the weights
Anonymous attendee 09:15 AM  
can we have the basic real life example comparing the  functio like tanh, with others so that we can have better clearity
Academic_Lead_SB 09:27 AM 
A simple way to think about it:
Sigmoid: Like a probability meter, giving values between 0 and 1.
Tanh: Like a sentiment scale, giving values between −1 (negative) and +1 (positive).
ReLU: Like an on/off switch—negative values become 0, positive values pass through.
Tanh is often preferred in RNNs because it can represent both positive and negative information, making it easier to model context and memory.
Sanchay Yadav 09:15 AM  
How it determined now it is last step?
Academic_Lead_SB 09:19 AM 
RNN takes the current word representation and the previous hidden state rep
Abdeali Dodiya 09:16 AM  
can i say like this ? 

RNN + BPTT = Gradient Problem
Acamdemic_Leads_SM 09:17 AM 
Yess, somewhat for long-term dependencies

RNN + BPTT can lead to vanishing and exploding gradient problems when learning long-term dependencies.
sauvik garai 09:19 AM  
h(t) is dependent on h(t-1)... is there any specific formula ?
Acamdemic_Leads_SM 09:22 AM 
Yes. The current hidden state is computed using the current input, the previous hidden state (memory), and some learnable weights and biases, followed by an activation function such as tanh. This allows the RNN to carry information from earlier time steps and use it when processing new inputs.
Rohit Venkata Ravi Kiran Namburu 09:20 AM  
How are we converting words to numbers to be used in RNN?
Vishnuvardhan_TA 09:22 AM 
Good question! Neural networks only understand math, so we have to translate text into numbers before feeding it into the RNN.

Remember last session, Word2Vec, Word embeddings , that s how we do it.
Vamsi Krishna Akhil Jonnalagadda 09:20 AM  
I missed the first 10 mins. Could anyone explain briefly?
Academic_Lead_SB 09:22 AM 
So we are sudying the RNN concept where the motivation is to analyze sequential data like text/audio. So we need to analyze the embeddings of the current input along with the representations of the previous inputs right? So here is where the Back prop over Time of RNN comes in ...
Ramakrishnan 09:21 AM  
its a memory issue to remember everything
Academic_Lead_SB 09:28 AM 
Vanishing and exploding gradients are fundamentally training problems. Vanishing gradients indirectly cause memory issues because the network struggles to learn and retain long-range dependencies.
Abdeali Dodiya 09:22 AM  
What exactly prevents the hidden state in a Vanilla RNN from retaining information over thousands of timesteps????
Academic_Lead_SB 09:23 AM 
prof is explaininf
Abdeali Dodiya 09:22 AM  
is vanishing gradient fundamentally training problem , memory problem or both??
Academic_Lead_SB 09:24 AM 
Vanishing gradient is fundamentally a training problem because the gradients become extremely small during backpropagation, making it difficult to update parameters associated with earlier time steps. However, it also leads to a memory problem in RNNs, since the model struggles to learn long-range dependencies and effectively "forgets" information from the distant past. So, it originates as a training issue but manifests as poor long-term memory.
prateek ranjan 09:22 AM  
Why do we calculate gradients at every time step
Acamdemic_Leads_SM 09:26 AM 
We calculate gradients at every time step because each input in the sequence contributes to the final prediction. The gradients tell us how much each timestep influenced the error, allowing the RNN to update its weights and learn which past information is important to remember or forget.
Lavanya G 09:24 AM  
If RNN is directed by chain rule - the step X depends on step X-1 right ? If we trace this back to the very first input, then it will remember and depend on first input. How does it get diluted ?
Vishnuvardhan_TA 09:27 AM 
You are 100% correct that mathematically, a continuous chain exists all the way back to the first input.

Lets walk through this

To find out exactly how much step 50 depends on step 1, the chain rule forces us to multiply the gradients (the weights and the tanh derivatives) for every single step in between.

BUT, What happens when you multiply a fraction by itself over and over? It shrinks exponentially.

0.5 * 0.5 = 0.25

0.25 * 0.5 = 0.125

If you do this across 50,000 words... the number practically becomes 0.


SO, The connection technically exists, but the signal gets multiplied by a fraction so many times that it shrinks to Zero,

Hope this helps :)
Abdeali Dodiya 09:24 AM  
If we increase the hidden state size of Vanilla RNN does it solve the long term dependency problem or does vanishing gradient still remain??
Chandan Kumar_TA 09:25 AM 
Increasing the hidden state size helps a little but does not solve the long-term dependency problem.
Larger hidden state gives the model more capacity to store information, but it cannot prevent the gradient from shrinking exponentially over long sequences.
Nabanita Das 09:25 AM  
what is the lraening rate?
Acamdemic_Leads_SM 09:26 AM 
Learning rate is a hyperparameter that controls how big a step the model takes when updating its weights during training.
Sapana pandey 09:26 AM  
is vanilla RNN actually used somewhere practically in real lfie , what could be the use cases
Chandan Kumar_TA 09:28 AM 
Vanilla RNN is rarely used in real production systems today.
We have further advanced models these days
Acamdemic_Leads_SM 09:28 AM 
Yess like sentiment classification, named entity recognition and also small machine translation tasks
Ramakrishnan 09:26 AM  
DLDW?
Acamdemic_Leads_SM 09:27 AM 
dL/dW means "the gradient of the loss (L) with respect to the weight (W)."

It tells us how much the loss will change if we slightly change a particular weight. During training, the optimizer uses this value to decide how to update the weight to reduce the loss.

In simple terms: dL/dW tells the model which direction and how much to adjust a weight to improve its predictions.
Bandna Uppal 09:28 AM  
Technical meaning of forget gate, what is the data structure behind this

Acamdemic_Leads_SM 09:29 AM 
The forget gate in an LSTM decides how much of the previous memory should be kept or discarded. Technically, it is a vector (tensor) of values between 0 and 1, where each value controls one part of the cell state's memory. It acts like a learnable filter that selectively forgets unimportant information and retains useful information.
Vamsi Krishna Akhil Jonnalagadda 09:29 AM  
What is RNN is simple terms? Just to analyze the audio? How does it interpret the audio? 
Academic_Lead_SB 09:30 AM 
An RNN (Recurrent Neural Network) is a neural network designed to process sequential data by remembering information from previous inputs. It is not just for audio. It can be used for text, speech, time-series data, and more.

For audio, the sound is first converted into a sequence of features (e.g., short chunks of the audio signal or spectrogram frames). The RNN processes these chunks one at a time, carrying forward a hidden state h_t that acts like memory. This allows it to understand how the sound changes over time, which is useful for tasks like speech recognition, speaker identification, and emotion detection.
Neha Persai 09:32 AM  
please can you explain candidature again ??
Acamdemic_Leads_SM 09:33 AM 
Candidate is the new information that an LSTM wants to store in its memory at the current time step. The input gate then decides how much of this new information should actually be added to the memory.
Vamsi Krishna Akhil Jonnalagadda 09:32 AM  
Got it. When is Vanilla RNN used here when it has no gates?
Academic_Lead_SB 09:34 AM 
A Vanilla RNN is mainly used for learning and for simple sequence tasks where only short-term dependencies matter. So the gated architecture comes in from LSTM
Sandipa Das 09:33 AM  
what is candidate?
Acamdemic_Leads_SM 09:34 AM 
Candidate is the new information that an LSTM wants to store in its memory at the current time step. The input gate then decides how much of this new information should actually be added to the memory.
Abhishek Singh 09:33 AM  
Why hidden state is coming after hidden state
Acamdemic_Leads_SM 09:34 AM 
The hidden state comes after the previous hidden state because an RNN is designed to remember past information. Each new hidden state is computed using the current input and the previous hidden state, so information can flow from one time step to the next. In simple terms, the previous hidden state acts as the network's memory, and the new hidden state is an updated version of that memory.
Shashank Maheshwari 09:33 AM  
Hello, While we are understanding the approach of how the learning occurs in RNN at a big picture- is it mandatory for Software Engineers to know each theorem/formula and should be able to compute the outputs ?
Vishnuvardhan_TA 09:39 AM 
That is a very practical question! Being a Software Engineer myself

The short answer is No, you do not need to compute these outputs by hand or memorize every single theorem.

BUT BUT BUT, let me stop the your happiness there, haha

You must understand the mathematical intuition. Why? Because when your model suddenly outputs NaN or flatlines during training, you need to know if it's a vanishing gradient problem or just a bug in your data pipeline.

One more example is, Knowing that tanh keeps numbers stable, or that a forget gate uses a sigmoid filter, allows you to debug effectively and choose the right architecture for your specific problem.

SO, Its like, Let the computer do the actual math. Our job as an engineer is to understand the behavior of the math sothat we can architect systems, debug failures, and optimize performance.
Ramakrishnan 09:34 AM  
what dh/dh t-1 and dc /dc t-1 h and c refers here?
Academic_Lead_SB 09:37 AM 
In an LSTM, h_t is the hidden state (current output) and c_t is the cell state (long-term memory). The term dh_t/dh_{t-1} measures how much the current hidden state depends on the previous hidden state, while dc_t/dc_{t-1} measures how much the current memory depends on the previous memory. Unlike a vanilla RNN, gradients can flow through c_t, allowing dc_t/dc_{t-1} to stay close to 1 and helping the network remember information over longer sequences.
Abhishek Singh 09:34 AM  
Sorry, why hidden state is coming after output gate..???
Acamdemic_Leads_SM 09:35 AM 
The output gate decides what part of the memory should be shown. The information that passes through the output gate becomes the hidden state. That's why the hidden state is generated after the output gate.
Anonymous attendee 09:34 AM  
how are the weights setup at t=1. Are they set to random values ?
Academic_Lead_SB 09:37 AM 
yes
Vamsi Krishna Akhil Jonnalagadda 09:35 AM  
So, is RNN mainly for AI model memory?
Acamdemic_Leads_SM 09:37 AM 
Yes. RNNs were designed to give neural networks a memory of previous inputs. Instead of processing each input independently, an RNN carries information from earlier time steps through its hidden state, allowing it to use past context when making predictions. This makes RNNs useful for sequential data such as text, speech, and time series.

For this reason RNN is used in time series data, which has sequential information
Shalmali 09:36 AM  
Abhishek Singh 09:36 AM  
got it, thanks!
Acamdemic_Leads_SM 09:37 AM 
Thanks
Vamsi Krishna Akhil Jonnalagadda 09:37 AM  
Also, how does LTSM know when to forget?
Chandan Kumar_TA 09:38 AM 
Over many training examples, the LSTM learns patterns like:
After seeing a new subject, forget information about the old subject
In this type of sentence, keep the earlier context
Academic_Lead_SB 09:39 AM 
using the forget gate ..... During training, it learns a value f_t between 0 and 1, where values close to 1 keep information and values close to 0 discard it. This allows the network to automatically retain useful information and forget irrelevant details.
Gurvinder Singh 09:38 AM  
what is candidate? can you explain again?
Acamdemic_Leads_SM 09:43 AM 
A candidate is the new information that the LSTM proposes to add to its memory at the current time step. It is called a candidate because the LSTM has not yet decided whether to store it. The input gate then decides how much of this proposed information should actually be added to the memory.
Ambica Badireddy 09:38 AM  
what if forget gate removes important information?
Chandan Kumar_TA 09:42 AM 
If important information is wrongly forgotten, the model's predictions will be poor.
This creates a high loss.
During backpropagation, the error signal flows back and updates the weights of the forget gate.
Lavanya G 09:38 AM  
RNN and LSTM both handle data under different distributions or same one because the activations for both of them is different no ? one is tanh and other is sigmoid 
Chandan Kumar_TA 09:41 AM 
No. RNN and LSTM generally handle data from the same type of distributions.
The choice of sigmoid and tanh helps the gates work properly (sigmoid gives 0-1 values, tanh gives -1 to 1), but the core improvement is the architecture design, not just the activation functions.
prateek ranjan 09:39 AM  
1. how do we expose what model is able to understand and what is not? 
2. How to make tweeks within the model / AI to eensure right information is being stored?
Acamdemic_Leads_SM 09:45 AM 
1. We analyze its behavior using attention maps, hidden states, activations, and test examples to see which information influences its predictions.
2. We cannot directly control it. Instead, through training, better architectures (LSTM/Transformer), and good data, the model learns to keep information that helps reduce prediction errors.
Vinod Krishnan 09:39 AM  
So in this example. the forget gate is 67.9% of the previous token? for instance if the phrase is the the cat is on the mat and  Ct-1 is cat the memory retains 67.9% of the vector that stores cat? is that a right understanding ?
Acamdemic_Leads_SM 09:40 AM 
Yes, that's mostly correct. A forget gate value of 67.9% means the LSTM keeps about 67.9% of the relevant memory information and forgets the rest. The important detail is that it operates on the memory vector's features, not directly on the word "cat" itself.
prateek ranjan 09:40 AM  
additionally how the forget information is being taken a call in terms of if model forgets information how to ensure only useless infromation is being forgotten
Acamdemic_Leads_SM 09:41 AM 
The LSTM does not know beforehand which information is useless. During training, it learns from its mistakes. If forgetting certain information hurts prediction accuracy, the model adjusts the forget gate to retain that information in the future. Over many training examples, the forget gate learns to keep useful information and discard information that does not help the task.
Sanchay Yadav 09:41 AM  
Will we also be cover gradient boosting methods in coming class such as XGBoost, LightGBM, and CatBoost?
Acamdemic_Leads_SM 09:43 AM 
No, these are machine learning models, here we disuss about deep learning, then NLP and transformers.
Anonymous attendee 09:42 AM  
When will the nwtweok stops learning ?
Chandan Kumar_TA 09:44 AM 
Basically on 4 conditions:
When we reach the maximum number of epochs we set before training.
Early stopping: When validation loss stops improving for several epochs in a row. This prevents overfitting.
When loss stops decreasing significantly (convergence). The model has learned as much as it can from the data with current settings.
When gradients become very small (vanishing gradient). The weights stop updating meaningfully.
Sandeep Chiluveru 09:42 AM  
Are all these question and answers are available for reference later ? I could not find the transcript for the last Sunday's lecture ....
Academic_Lead_SB 09:44 AM 
yes the QnA are available, the lecture 2 will be updated soon. The lecture 1 is there for your ref
Anonymous attendee 09:44 AM  
Ananya Pandey 09:44 AM  
How does Candidate state infleunce the cell state exactly ?
Acamdemic_Leads_SM 09:45 AM 
The candidate state contains the new information that could be added to memory. The input gate decides how much of this candidate information should be written into the cell state. So, the candidate state influences the cell state by providing the new memory content, while the input gate controls how much of it is actually stored.
prateek ranjan 09:47 AM  
how to choose between sigmoid and tanh, and in RNN - the sigmoid and TanH how do we define better piece 
does RNN only uses TanH ?
Vishnuvardhan_TA 09:49 AM 
We use Sigmoid when we need to make a yes/no decision or a percentage. Because it outputs between 0 and 1, it is perfect for Gates (like in an LSTM). 0 means "block this data" and 1 means "let it pass."

We use Tanh when we are calculating actual information. Because it goes from -1 to 1 (zero-centered), it can represent both positive and negative directions, example, "increase importance" vs "decrease importance"

In standard practice, yes! For a Vanilla RNN, the hidden state update almost exclusively uses Tanh. If we tried to use Sigmoid for a Vanilla RNN, its gradients are so small that the vanishing gradient problem would happen almost instantly!
Varadarajan Krishnan 09:48 AM  
If there is a dependency, and if any step deviates, the entire path will deviate due to the chaining dependency, wouldn't that be a problem?
Acamdemic_Leads_SM 09:51 AM 
Yes, that can be a problem. In an RNN, each step depends on the memory from the previous step, so if important information is lost or distorted early on, that error can propagate through the rest of the sequence. This chaining dependency makes it difficult for vanilla RNNs to preserve information over long sequences, which is why architectures like LSTMs and GRUs were introduced to better protect important information.
Kavya Srinivasan 09:48 AM  
How much inofrmation can a fixed vector store? Is there a limit for that?
Vishnuvardhan_TA 09:54 AM 
A fixed vector has a set number of dimensions

for example, 512 numbers. You cannot mathematically pack an infinitely long book into exactly 512 numbers without throwing something away

When an LSTM reaches its limit, it doesn't crash it just starts blurring the information. It keeps a vague, overall summary of the document but completely loses specific, high-resolution details.
Vamsi Krishna Akhil Jonnalagadda 09:51 AM  
How do we know when we should alter the states like mentioned in this question? Is there any standard that we should follow?
Acamdemic_Leads_SM 09:52 AM 
There is no fixed rule that tells the model when to alter its states. The model learns this automatically during training. If changing or retaining certain information helps reduce prediction errors, the training process adjusts the weights so that the hidden states and gates behave accordingly. In practice, we rely on the training data, loss function, and architecture (RNN, LSTM, GRU, Transformer) rather than manually specifying when states should be changed.
Abhishek Ameta 09:52 AM  
IF we had to use a model B/W RNN or LSTM for a smaller text data (like emails) than which model should be better RNN or LSTM, does inference time will play important role?
Acamdemic_Leads_SM 09:53 AM 
For small text sequences such as emails, LSTM is usually the safer choice because it can remember important context better than a vanilla RNN. If the emails are very short and the task is simple, an RNN may perform similarly while being slightly faster and having fewer parameters. However, in most real-world cases, the inference-time difference between RNN and LSTM is relatively small compared to the potential gain in accuracy and stability from using an LSTM. Therefore, accuracy is usually the deciding factor, not inference time.
Sanchay Yadav 09:54 AM  
more dimension then more capacity but it don’t solve long range?
Acamdemic_Leads_SM 09:54 AM 
Yes. Increasing the hidden-state dimension gives the model more capacity to store information, but it does not solve the long-range dependency problem.

A larger hidden state means the model has more memory space, but information still has to travel through many timesteps. As the sequence gets longer, important information can still be overwritten or become difficult to learn due to vanishing gradients. This is why simply increasing the hidden-state size is usually not enough; architectures like LSTMs and GRUs were designed to better preserve information over long sequences.
Ramakrishnan 09:55 AM  
A. option A LSTM three times it will come same right consisteny of the tool is not there right
Acamdemic_Leads_SM 10:01 AM 
This an model preprocessing method, but option D is more correct
Abhishek Singh 09:56 AM  
Question explicityly says that we have to write most reasonable engineering response. SO I think option 1 is right not option 4
Acamdemic_Leads_SM 10:00 AM 
In terms of engineering perspective all the 3 options are correct. But option 4 is the more approriate answer.
Abdeali Dodiya 09:56 AM  
So LSTM problem will solve transformer ? 
Acamdemic_Leads_SM 09:59 AM 
Yess
Jasleen Kaur 10:02 AM  
how we knoe layer is 3
Acamdemic_Leads_SM 10:07 AM 
Please go to the documentation of ElmoEmbedder class. It show have number of layers kind of things as arguments.
Anonymous attendee 10:02 AM  
Anonymous attendee 10:03 AM  
is 1024 in embedding dimension?
Academic_Lead_SB 10:03 AM 
yes
Lavanya G 10:04 AM  
When we say we have the embedding at emb[2][5] would it be a result of both forward feed and back prop ?
Vishnuvardhan_TA 10:08 AM 
We only use backprop to teach the model and update its weights. Once it is trained, backprop is turned off.

Both Directions here means Reading, not Training

When we generate that embedding (emb[2][5]), we are just doing a standard forward feed (inference). 

Also, because ELMo uses a Bidirectional LSTM, it actually reads the sentence in two directions at the same time:

It reads the sentence left-to-right (Forward LSTM).

It reads the sentence right-to-left (Backward LSTM).
Ravi prasad Reddy Soda (You) 10:07 AM  
doesn't ELMo use more memory and computation to traverse the same sentence two times from both directions ?
Lavanya G 10:07 AM  
At what point do we decide whether we will do a back prop or forward feed ? 
Acamdemic_Leads_SM 10:07 AM 
Forward pass is used to make a prediction. Backpropagation is used during training, after computing the prediction error, to update the model's weights. During inference, only the forward pass is used.
Varadarajan Krishnan 10:07 AM  
The bank in another sentence could mean very similar in reference to each other. So will that also have a different vector

I went to the bank today

The bank is closed today

How will these two be handled?
Acamdemic_Leads_SM 10:09 AM 
In Word2Vec/GloVe, "bank" will have the same vector in both sentences. In BERT-like models, it will have slightly different vectors because the surrounding context is different, but the vectors will still be very similar since the meaning is the same.
Vamsi Krishna Akhil Jonnalagadda 10:08 AM  
Word2Vec always preferable or are there any use cases for Word2Vec and ELMO?
Acamdemic_Leads_SM 10:10 AM 
Word2Vec is faster and simpler, so it is useful when context is less important. ELMo understands context, so the same word can have different meanings in different sentences. Use Word2Vec for efficiency and ELMo for better contextual understanding.
prateek ranjan 10:08 AM  
does ELMO and LSTM work with same amount of memory and ELMO results in reainting more infromation in same data size
Acamdemic_Leads_SM 10:10 AM 
No. ELMo typically uses more memory than a standard LSTM because ELMo is built using multiple bidirectional LSTMs and generates contextual embeddings for every word.

ELMo can often retain and use more contextual information than a simple LSTM because it processes words using both left and right context. However, this improvement comes from a more sophisticated architecture, not because it stores more information in the same memory size.
Sravya G 10:11 AM  
Can you explain what LSTM stacking vs widening the LSTM mean?
Academic_Lead_SB 10:13 AM 
stacking -> more number of layers 
Widening -> increading the number of hidden units in a layer
Abhishek Singh 10:13 AM  
I must say all these questions are really great, so whoever has designed them kudos to him!
Academic_Lead_SB 10:14 AM 
thanks
Acamdemic_Leads_SM 10:14 AM 
Thanks
Neha Persai 10:15 AM  
could you please explain how actually BiLSTM works in terms pf ELMO embedding?
Acamdemic_Leads_SM 10:15 AM 
In ELMo, a BiLSTM uses two LSTMs: one reads the sentence left-to-right and the other right-to-left. For each word, ELMo combines information from both directions, allowing the word's embedding to depend on its surrounding context. This helps ELMo understand the meaning of a word based on the sentence it appears in.
10:15 AM  




