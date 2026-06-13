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

Neha Persai 10:15 AM 
could you please explain how actually BiLSTM works in terms pf ELMO embedding?
Acamdemic_Leads_SM 10:15 AM 
In ELMo, a BiLSTM uses two LSTMs: one reads the sentence left-to-right and the other right-to-left. For each word, ELMo combines information from both directions, allowing the word's embedding to depend on its surrounding context. This helps ELMo understand the meaning of a word based on the sentence it appears in.
Dron Garg 10:15 AM 
we are leading to transformers and CNN, RNN, LSTM etc are good to know but do we need to remember these? Are these still used in industry ?
Acamdemic_Leads_SM 10:16 AM 
You need to remeber the core concepts, not much more mathematical notations

we are leading to transformers and CNN, RNN, LSTM etc are good to know but do we need to remember these? Are these still used in industry ?
Acamdemic_Leads_SM 10:16 AM 
You need to remeber the core concepts, not much more mathematical notations


Sandeep Chiluveru 10:18 AM  
query 1: So ... given that both RNN LSTM and Transformers consume same amount of power and compute time ... the choice should always be a Transformer over an RNN ? 
query 2: RNN's too may have some uses? Especially if they are more efficient in shorter sequences of data
Vishnuvardhan_TA 10:24 AM 
Good Q!, These two questions go perfectly together! 

To answer Query 1, They do NOT consume the same amount of power or memory!

Transformers train extremely fast because they do everything in parallel. BUT, they are massive memory consumers. Their memory requirement grows with sequence length.

Transformers are the kings of massive NLP tasks

BUT BUT, heear me out, LSTMs absolutely dominate in these areas

1. Real-Time Streaming, If you are processing live data (like a live stock ticker)
2. Edge Devices, Because their memory footprint is so small, LSTMs can run locally on smartwatches, IoT sensors, and mobile phones where a massive Transformer would crash the device.
3. Short Time-Series Data, For simple sequential numerical data (like daily temperature readings or heart-rate monitoring), an LSTM is much more efficient and will get the job done perfectly

These are just some examples but you can obviosuly find more
Sandeep Chiluveru 10:20 AM  
Or in put in other way are Transformers always better than RNN and CNN or do RNN and CNN also have their use cases and advantages ?

Academic_Leads_SM 10:27 AM 
No. Transformers usually perform best, especially for long-range dependencies, but they require more data and computation. RNNs are useful for sequential/streaming data, and CNNs are efficient for capturing local patterns. The best choice depends on the task and resource constraints.
Vishnuvardhan_TA 10:27 AM 
It is very tempting to think Transformers replaced everything, but they absolutely did not. Deep Learning is a toolkit, and every architecture still has a specific job.

Lets do CNNs vs Transformers

Transformers only win if you have massive datasets (millions of images) and huge server farms. If you are building a computer vision app for a phone, or only have a few thousand training images, CNNs are still the undisputed kings.

If we take RNNs vs Transformers

If you are analyzing a live heartbeat monitor, processing a live stock feed, or running a voice assistant on a tiny smartwatch chip, RNNs are the standard.
Sharad Kumar 10:23 AM  
From Industry application purpose now we have LLM like Gemini, Grok, Claud where they are giving the option of skill, context management and prompt management which imply we dont have to work on all the pre attentation architecture. From business applaction perspective, how I can ustilize the older approach knowledge to figure out new business appliction implemetation which utilizes the LLM and Agents?
Vishnuvardhan_TA 10:30 AM 
LLMs (like Gemini or Claude) are massive and are expensive and have high latency. If your business needs to process millions of live server logs or IoT sensor pings per second, an LLM API is too slow and too costly. Your knowledge of lightweight LSTMs/RNNs allows you to build something that runs locally for pennies.

In modern enterprise apps, the LLM is just the "Manager" An advanced Agentic workflow will use an LLM to understand the user's intent, but then the LLM will route the actual task to a specialized older model! You can refer skills, tools, etc for this.

You don't build modern apps by throwing an LLM at every single problem. You use LLMs to orchestrate, and you use your foundational architecture knowledge to build the efficient, targeted tools the LLM relies on!
Sharad Kumar 10:23 AM  
From Industry application purpose now we have LLM like Gemini, Grok, Claud where they are giving the option of skill, context management and prompt management which imply we dont have to work on all the pre attentation architecture. From business applaction perspective, how I can ustilize the older approach knowledge to figure out new business appliction implemetation which utilizes the LLM and Agents?
Vishnuvardhan_TA 10:30 AM 
LLMs (like Gemini or Claude) are massive and are expensive and have high latency. If your business needs to process millions of live server logs or IoT sensor pings per second, an LLM API is too slow and too costly. Your knowledge of lightweight LSTMs/RNNs allows you to build something that runs locally for pennies.

In modern enterprise apps, the LLM is just the "Manager" An advanced Agentic workflow will use an LLM to understand the user's intent, but then the LLM will route the actual task to a specialized older model! You can refer skills, tools, etc for this.

You don't build modern apps by throwing an LLM at every single problem. You use LLMs to orchestrate, and you use your foundational architecture knowledge to build the efficient, targeted tools the LLM relies on!
bhanupriya katrapally 10:26 AM 
so can we say LSTM can be used for processing huge sequential data
Academic_Leads_SM 10:27 AM 
LSTMs can process long sequential data better than vanilla RNNs because they can retain information for longer periods. However, for very long sequences, Transformers are generally more effective because they can access distant information more directly.

Sharad Kumar 10:23 AM 
From Industry application purpose now we have LLM like 
Vishnuvardhan_TA 10:30 AM 
LLMs (like Gemini or Claude) are massive and are 
Sharad Kumar 10:23 AM  
From Industry application purpose now we have LLM like Gemini, Grok, Claud where they are giving the option of skill, context management and prompt management which imply we dont have to work on all the pre attentation architecture. From business applaction perspective, how I can ustilize the older approach knowledge to figure out new business appliction implemetation which utilizes the LLM and Agents?
Vishnuvardhan_TA 10:30 AM 
LLMs (like Gemini or Claude) are massive and are expensive and have high latency. If your business needs to process millions of live server logs or IoT sensor pings per second, an LLM API is too slow and too costly. Your knowledge of lightweight LSTMs/RNNs allows you to build something that runs locally for pennies.

In modern enterprise apps, the LLM is just the "Manager" An advanced Agentic workflow will use an LLM to understand the user's intent, but then the LLM will route the actual task to a specialized older model! You can refer skills, tools, etc for this.

You don't build modern apps by throwing an LLM at every single problem. You use LLMs to orchestrate, and you use your foundational architecture knowledge to build the efficient, targeted tools the LLM relies on!
bhanupriya katrapally 10:26 AM 
so can we say LSTM can be used for processing huge sequential data
Academic_Leads_SM 10:27 AM 
LSTMs can process long sequential data better than vanilla RNNs because they can retain information for longer periods. However, for very long sequences, Transformers are generally more effective because they can access distant information more directly.


Sanjivani Hoderker 10:32 AM 
Please explain exploding gradient problem again
Vishnuvardhan_TA 10:36 AM 
It is the exact opposite of the Vanishing Gradient problem.

Earlier we talked about how the Vanishing Gradient happens when we repeatedly multiply fractions (0.5 * 0.5 = 0.25), causing the signal to shrink to zero.

The Exploding Gradient happens when the network's weights are slightly greater than 1.

If you multiply a number larger than 1 by itself over and over, it grows exponentially.

1.5 * 1.5 = 2.25

2.25 * 1.5 = 3.375

If you do this across 50 words... the number explodes to over 600 million!



This is one analogy i use for my understanding 
Vinod Krishnan 10:34 AM  
rookie question: why is the hidden state named hidden? is it because it is transient in memory?
Chandan Kumar_TA 10:37 AM 
The hidden state is called hidden because it is not directly visible to the outside world.
Srushti Anant Shimpi 10:34 AM  
How does the forget gate in LSTM decide what information is important enough to keep over many time steps?
Academic_Lead_SB 10:37 AM 
prof is addressing this question
Aashish Juneja 10:38 AM 
Can we get reference books that can help us out in this journey there are lots of books on cloud library, but the order we should follow those or any specific reference books we should follow. Can you guide us. Or these slides are sufficient?
Academic_Lead_SB 10:39 AM 
you can refer to the pre-read and post-read books.


Ganesh Bathula 10:41 AM 
Are transformers better than RNNs for all sequence tasks, or do RNNs still have advantages?
Academic_Leads_SM 10:44 AM 
No, Transformers are not always better. Transformers generally achieve better performance on most sequence tasks because they can capture long-range dependencies and train efficiently in parallel. However, RNNs and LSTMs still have advantages in some situations, such as streaming or real-time data where inputs arrive one step at a time, and in resource-constrained environments where memory and computation are limited. So, Transformers are usually the preferred choice, but RNNs can still be useful when efficiency, latency, or sequential processing is important.


Bandna Uppal 10:41 AM  
Which popular applications using RNN and LSTMs based models still

Academic_Leads_SM 10:44 AM 
RNNs and LSTMs are still commonly used in time-series forecasting, anomaly detection, predictive maintenance, sensor/IoT data analysis, and some speech-processing applications. While Transformers dominate modern NLP, LSTMs remain useful when data arrives sequentially and computational efficiency is important.
Ganesh Bathula 10:41 AM  
Are transformers better than RNNs for all sequence tasks, or do RNNs still have advantages?
Academic_Leads_SM 10:44 AM 
No, Transformers are not always better. Transformers generally achieve better performance on most sequence tasks because they can capture long-range dependencies and train efficiently in parallel. However, RNNs and LSTMs still have advantages in some situations, such as streaming or real-time data where inputs arrive one step at a time, and in resource-constrained environments where memory and computation are limited. So, Transformers are usually the preferred choice, but RNNs can still be useful when efficiency, latency, or sequential processing is important.
Nirupam Gupta 10:41 AM  
BiLSTM & Backpropogation, how are they diffrent?
Vishnuvardhan_TA 10:46 AM 
This is understandable mix-up! It happens because Deep Learning uses the word "backward" for two totally different things.

BiLSTM is the Architecture (the structure of the brain). It is how the model is built to read sentences. In BiLSTM, "backward" means reading the text from right to left (e.g., reading "The cat sat" as "sat cat The").

Backpropagation is the Training Algorithm (the learning process). It is just the calculus used to update the model's weights when it makes a mistake. In Backpropagation, "backward" means sending the error score backward through the math layers to correct the model's mistakes.

REMEMBER THIS,

Backpropagation ONLY happens in the lab during the Training Phase. Once the model learns the task, backprop is turned off completely.

BiLSTM happens every single time you use the model during Inference. It always has to read the sentence in both directions to understand the context, even after it is fully trained!
Aashish Juneja 10:43 AM  
So pre reads and post reads materials are sufficient. Looking for guidance so that we won't go too much deep into one topic that we missed the learning of important topics coming ahead. So when to move and where to go deep type of guidance I am looking for
Academic_Lead_SB 10:51 AM 
Yes more or less the Essential and Additional Pre-reads and post-reads covers the entire lecture slide info that are being covered. You can also refer to other sources if you want
Varadarajan Krishnan 10:47 AM  
A follow up to the previous question, if I give a very long sentence which is completely nonsenical or is too complex with multiple commas in the sentence, how will it be interpreted, because commas breaks the sentences and multiple things can be said in the same sentence, similarly I may have exclamation words like Oh, yuck, . How are these interpreted?
Academic_Leads_SM 10:48 AM 
Modern models do not treat commas or words like "Oh" and "Yuck" as hard sentence breaks. They are treated as tokens that carry meaning and context. During training, the model learns that commas often indicate pauses, clause boundaries, or relationships between ideas, while words like "Oh", "Wow", or "Yuck" convey emotion or sentiment. If a sentence is very long or complex, the model tries to use all these signals to understand the structure. However, if the sentence is completely nonsensical or contains too many nested ideas, the model may become less confident and produce less accurate interpretations because the underlying meaning itself is unclear, not because of the commas or punctuation.
Sandeep Chiluveru 10:50 AM  
... as an extension to my query between the following two strategies which might be better (better ...depends on use case in question of course)
Which of the following options is better, let's say for time series data?
- Train a model over a large data set once and use it for predictions
- Train continously/frequently over smaller datasets and get back predictions.
The answer is probably subjective, but I am curious to know ...about industry and expert opinion on best practice 
...

Academic_Leads_SM 10:51 AM 
It depends on whether the data changes over time. If the data is relatively stable, training once on a large dataset usually works best because the model learns more robust patterns. If the data changes frequently (e.g., stock prices, user behavior), regular retraining on recent data helps the model stay up to date. In practice, many industry systems use a hybrid approach: train on a large historical dataset and periodically retrain with new data.
Ravi prasad Reddy Soda (You) 10:51 AM  
is context calculated at each step ?
Academic_Leads_SM 10:52 AM 
Yes. Context is updated at every step as new information arrives. In RNNs/LSTMs, this happens through the hidden state, while in Transformers it happens through the attention mechanism.
Lavanya G 10:52 AM  
if forward pass is used to make predictions and we do a feed forward for the dynamic context how does it learn ? I am missing something here 
Academic_Leads_SM 10:53 AM 
The forward pass updates the context and makes a prediction, but it does not learn. Learning happens afterward, when the model compares its prediction with the correct answer and uses backpropagation to update its weights.
Vamsi Krishna Akhil Jonnalagadda 10:53 AM  
Because we have transformer architecture, we don't need to use RNN and Attention?
Academic_Leads_SM 10:55 AM 
No. Transformers have largely replaced RNNs in NLP because they handle long-range context better using attention. However, RNNs/LSTMs are still useful in some streaming and resource-constrained applications.
Vinod Krishnan 10:54 AM  
is there a mathematical representation of the attention layer? similar to the one that was shown as worked out exmaple for the RNN.? that was very helpful to comprehend
Academic_Leads_SM 10:58 AM 
Attention = compare all tokens → assign importance scores → combine the most relevant information.
Lavanya G 10:54 AM  
Does this mean the dynamic context also can get updated after the back prop ?
Academic_Lead_SB 10:58 AM 
Not exactly. The dynamic context (hidden states such as h_t and c_t) is computed during the forward pass and is not directly updated during backpropagation. Backpropagation updates the model parameters (weights and biases). On the next training iteration, those updated parameters produce different hidden states and cell states. So, backpropagation changes the model's ability to create context, rather than modifying the already-computed context itself.
Srushti Anant Shimpi 10:58 AM  
In LSTMs, memory is compressed into a fixed hidden state, whereas Transformers can attend directly to all previous tokens. Does this mean Transformers are performing retrieval rather than memorization, and is that the deeper reason they outperform recurrent architectures?
Vishnuvardhan_TA 11:02 AM 
Yes, you are exactly right. The shift from LSTMs to Transformers is literally the shift from Lossy Compression to Dynamic Retrieval.

An LSTM has to squeeze the entire history of a document into a single, fixed-size vector. By the time it reaches word 1,000, it is mathematically forced to overwrite or forget early details to make room for new ones. It is lossy compression.

Transformers completely refuse to summarize. Instead, the Attention mechanism acts like a search engine. It keeps every single previous word perfectly intact in its memory (the KV Cache). The current word acts as a Query, searching all previous words (Keys) to instantly Retrieve exactly the information (Values) it needs.

By using retrieval instead of a rolling memory, Transformers completely destroy the Information Bottleneck. The mathematical distance between the first word and the last word is always exactly 1 step.
Komal 11:00 AM  
Are transformers better than CNNs and RNNs? When do we use each of them? can we get some examples?
Academic_Leads_SM 11:03 AM 
Transformers: Best for text and long-range context (e.g., ChatGPT, translation).
RNNs/LSTMs: Good for sequential or streaming data (e.g., time-series forecasting).
CNNs: Best for images and local pattern detection (e.g., image classification).

Rule of thumb: Transformers for language, CNNs for vision, and RNNs/LSTMs for some sequence and real-time tasks.
Anonymous attendee 11:06 AM  
What is input and output embedding ?
Academic_Leads_SM 11:07 AM 
Input embedding converts words or tokens into numerical vectors that the model can understand.

Output embedding converts the model's internal representation back into scores/probabilities over the vocabulary to predict the next word or token.
Vamsi Krishna Akhil Jonnalagadda 11:06 AM  
Explain transformation architecture in simple words?
Academic_Leads_SM 11:08 AM 
In simple terms, a Transformer is a model that reads all words in a sentence at the same time and uses attention to determine which words are most relevant to each other.

For example, in:

"The animal didn't cross the street because it was tired."

The Transformer can learn that "it" refers to "animal" by paying attention to the relevant words, even if they are far apart.

Unlike RNNs, which process words one by one, Transformers process the entire sequence together, making them faster and better at capturing long-range relationships.
Pushkaraj Shingre 11:09 AM  
So does decoder also run in parallel? If yes, its job is to predict next token, so how without predicting next token it can have parallelism?
Academic_Leads_SM 11:11 AM 
Decoder will be discussed in upcoming lecture
Anonymous attendee 11:10 AM  
Are we going to cover all these concepts in hands-on session today?
Academic_Lead_SB 11:20 AM 
we will have a CNN and RNN tutorial today the attention will be covered in tutorial next week
Kumar Baibhav 11:10 AM  
Basic Question, what is token ?
Academic_Leads_SM 11:11 AM 
A token is the basic unit of text that a model processes. A token can be a word, part of a word, punctuation mark, or even a single character, depending on the tokenizer.

For example:

"I love machine learning!"

might be split into tokens like:

"I"
"love"
"machine"
"learning"
"!"
Gurvinder Singh 11:11 AM  
if a doc has 1 million word..all one million word will be compared with each other?
Vishnuvardhan_TA 11:14 AM 
You have just identified the biggest mathematical roadblock in all of modern Deep Learning! It is called the "Quadratic Bottleneck" or the O(N^2) problem.

Mathematically, the base Attention formula wants to compare every word to every other word.

10 words = 100 connections.

1,000 words = 1,000,000 connections.

1,000,000 words = 1 Trillion connections!

Because the Transformer calculates everything in parallel, it has to hold all 1 Trillion of those connection scores in the computer's memory at the exact same time. For a standard 1-million-word document, a traditional Transformer would instantly crash even the most powerful supercomputer because it simply runs out of RAM.
prateek ranjan 11:11 AM  
encoder = attention, feed forward, non linear activation what were 3 bullets for decoder?
Academic_Leads_SM 11:31 AM 
Decoder

Masked Self-Attention
Cross-Attention (to encoder output)
Feed-Forward Network + Non-linear Activation
Varadarajan Krishnan 11:11 AM  
Parallelism also will have some limits, and if you break the no. of parallel processing words, that can it can distort if the entire sentence is not considered together, is that right?
Academic_Leads_SM 11:14 AM 
Yes. While Transformers process tokens in parallel, they still use attention to consider relationships across the sentence. However, if the text is split into chunks because of context limits, the model may miss connections between chunks, which can reduce accuracy.
Manikandan Veeraraghavan 11:12 AM  
how does this work for non-english language?
Academic_Leads_SM 11:14 AM 
For non-English languages, the process is essentially the same. The text is first broken into tokens, and the Transformer learns relationships between those tokens using attention. Modern multilingual models are trained on many languages, so they learn patterns, grammar, and word relationships across different languages. As long as the language was well represented during training, the model can process it similarly to English.
Vamsi Krishna Akhil Jonnalagadda 11:12 AM  
Hows the score and weight calculated here?
Academic_Leads_SM 11:14 AM 
In a Transformer, the attention score measures how relevant one token is to another. The model learns this automatically during training by comparing token representations (queries and keys). These scores are then converted into weights, which determine how much attention each token should receive when building the final context representation.

In simple terms:

The model calculates a relevance score between tokens.
The scores are normalized into weights.
Higher weights mean the model pays more attention to those tokens.
These weights are learned indirectly through training to improve prediction accuracy.
Sandeep Chiluveru 11:12 AM  
So .. is Transformer a Deep Neural Network with attention ?
 
Academic_Leads_SM 11:16 AM 
Yes. A Transformer is a type of deep neural network whose core mechanism is attention.

It consists of multiple neural network layers, and instead of using recurrence (RNNs), it uses self-attention to learn relationships between tokens. So, a simple way to think about it is:

Transformer = Deep Neural Network + Attention Mechanism + Positional Information

This combination allows it to understand context and long-range dependencies very effectively.
Vinod Krishnan 11:14 AM  
is the Key matrix preconfigured and preloaded ? like a lookup? and are there Key matrices specific to industries?
Vishnuvardhan_TA 11:18 AM 
No, it is not a static lookup table, it is generated dynamically!

When you use a Transformer, the Q, K, and V vectors do not exist in a saved database somewhere. They are created on the fly.

Regarding Industry specifc part, Yes, but we don't just swap out a lookup table. We use a process called Fine-Tuning.
Kumar Baibhav 11:15 AM  
how do we preserve semantics in token, is it necessary that tokens has to be in order ?
Academic_Leads_SM 11:16 AM 
Using Positional Encoding, these method will discuss in the upcoming slides
Jasleen Kaur 11:18 AM  
why transformers are impt for agentic ai
Academic_Leads_SM 11:18 AM 
Transformers are important for Agentic AI because they provide the strong language understanding and reasoning capabilities that agents rely on. Using attention, Transformers can understand instructions, maintain context, interpret documents, generate plans, and decide which tools to use.

In simple terms:

Transformers are the "brain" of many AI agents.

They enable agents to understand goals, break tasks into steps, interact with tools, and generate responses, while the agent framework adds memory, planning, and tool execution on top of the Transformer.
Anirban Chakraborty 11:19 AM  
Can query be discussed in more detail? What is the depth and number of queries - to understand natural language nuances there can be a lot of queries which can be asked to infer key and value strength
Academic_Leads_SM 11:21 AM 
Yes. A useful way to think about a query is that it represents what a token is looking for in the rest of the sequence. The model does not create human-readable questions such as "Who is the subject?" or "What does 'it' refer to?". Instead, it learns vector representations that implicitly capture these needs.

There is one query per token per attention head. So if a sentence has 100 tokens and the model has 12 attention heads, there are effectively 1,200 query vectors being computed in that layer. Different heads often learn to focus on different relationships, such as grammar, entities, sentiment, long-range dependencies, or coreference.

The "depth" comes from the fact that this process happens across many Transformer layers. Early layers may learn simpler relationships, while deeper layers combine information into more abstract concepts. As a result, the model does not rely on a single query to understand language. It uses many queries across many heads and many layers, allowing it to capture a wide range
sauvik garai 11:19 AM  
how to get attention score from keys and queries ?
Academic_Leads_SM 11:22 AM 
The attention score is obtained by comparing a query with each key. The more similar the query and key are, the higher the attention score.

In simple terms:

A token creates a query ("What am I looking for?").
It compares this query with all keys in the sequence.
Similar keys receive higher scores.
These scores are converted into attention weights.
The weights determine how much information is taken from the corresponding values.
Shashank Maheshwari 11:20 AM  
When we say here 2 tokens- so the model removes all unncessary keywords and then focus on the tokens that matter? if yes, what is this process called? what if any key tokens or words are missed during this process?
Academic_Leads_SM 11:21 AM 
Not exactly. The model does not remove words first. It processes all tokens, but the attention mechanism assigns higher weights to more relevant tokens and lower weights to less relevant ones.

This process is called attention (or self-attention in Transformers).

If an important token receives too little attention, the model may misunderstand the context and produce a less accurate result. Training helps the model learn which tokens are usually important for a given task.
avishek kumar sinha 11:21 AM  
can you please explain softmax calculation
Academic_Lead_SB 11:22 AM 
Softmax(z_i) = e^{z_i}/ sum_j e^{z_j}
Vamsi Krishna Akhil Jonnalagadda 11:22 AM  
How does this attention work?
Academic_Lead_SB 11:28 AM 
Attention works by comparing the current word with all other words in the sequence and assigning an importance score to each one. These scores are converted into weights using Softmax, and the model computes a weighted combination of the corresponding word representations. Words with higher weights contribute more to the final representation, allowing the model to focus on the most relevant context when processing a token.
avishek kumar sinha 11:23 AM  
explain in details please
Academic_Lead_SB 11:26 AM 
Self-attention is a type of attention where each word in a sequence looks at all the other words in the same sequence to determine which ones are most relevant. It assigns attention weights to the words and uses them to build a richer representation of the current word. For example, in the sentence "The animal didn't cross the street because it was tired", the word "it" can pay more attention to "animal" than to "street", helping the model understand the context more accurately.
Gurvinder Singh 11:25 AM  
so how are these problems solved? working on small different dataset?
Academic_Leads_SM 11:26 AM 
Which problem can more elaborate it?
avishek kumar sinha 11:27 AM  
how mathmatics works here in softmax
Chandan Kumar_TA 11:30 AM 
In attention, the raw scores from query key dot product can be any real numbers. Softmax converts these into attention weights between 0 and 1 that sum to 1.
Chandan Kumar_TA 11:36 AM 
Just to add, Scaling also is an Interim process between dotproduct and Softmax conversion.
Gurvinder Singh 11:27 AM  
of i million words being related to each other in a large doc
Academic_Leads_SM 11:30 AM 
can you frame the whole question? otherwise it difficult to answer.
Pushkaraj Shingre 11:27 AM  
Where does positional encoding comes into play here? can you pls explain. 
Academic_Leads_SM 11:28 AM 
Positional encoding is added before the attention mechanism because attention itself does not know the order of tokens.

For example:

"Dog bites man"
"Man bites dog"

contain the same words, but the meaning changes because of the order.

To preserve this order information, each token embedding is combined with a positional encoding that tells the model where the token appears in the sequence. The attention mechanism then uses both:

What the token is (embedding)
Where the token is (positional encoding)

This allows the Transformer to understand word order and sentence structure while still processing all tokens in parallel.
Vinod Krishnan 11:28 AM  
the magic here was the WV weight matrix, if that was 0,1:1,0 we will get animal = 0,0.27 and it as 0.27,0 so how does the system get the the best WV weight matrix? same question for Key? if its generated dynamically how does it assign keys like animal is closer to noun so is “IT”?
Academic_Leads_SM 11:32 AM 
The (W_Q), (W_K), and (W_V) matrices start with random values and are learned during training through backpropagation The model is never told that "animal" is a noun or that "it" refers to "animal". Instead, it learns that connecting these words helps reduce prediction errors. Over time, the weights adjust so that related words produce similar queries and keys, resulting in higher attention scores.
Jasleen Kaur 11:28 AM  
in feed forward layer do we have hidden weights?
Academic_Leads_SM 11:28 AM 
Yes. A feed-forward layer contains learnable weights and biases, often called the layer's parameters.

In a Transformer, after attention, the token representations pass through a feed-forward neural network. This network has one or more layers of hidden weights that learn how to transform the representation into a more useful form.
prateek ranjan 11:28 AM  
what is relu?
Academic_Leads_SM 11:29 AM 
It is non Linear activation function.

ReLU(x)=max(0,x)
swapnil vaze 11:32 AM  
If there are millions of words then how this comparison is handled, somewhere you mentioned this problem as "Quadratic Bottleneck"?
Academic_Leads_SM 11:34 AM 
Yes. In standard self-attention, every token compares with every other token, so the computation grows very quickly as the sequence gets longer. This is called the quadratic bottleneck. For very long documents, models avoid this by using chunking, retrieval (RAG), sparse attention, or memory mechanisms so that only the most relevant information is processed.
Aashish Juneja 11:32 AM  
Just out of curiosity, can you please help me how all these mathematical formula understanding and calculations will help me in future practical session if everything I have to do via Python libraries. How much I should go deep into it for understanding to move ahead learning of Gen AI and Agentic AI program?
Academic_Lead_SB 11:34 AM 
You do not need to be able to derive every equation or implement every layer from scratch to work effectively with GenAI and Agentic AI. However, understanding the intuition behind concepts such as embeddings, attention, softmax, gradients, transformers, and retrieval helps you reason about model behavior, debug issues, choose the right architecture, and explain decisions to stakeholders.
For most industry roles involving LLMs, RAG, agents, and AI applications, a strong conceptual understanding combined with hands-on experience using frameworks and APIs is usually far more valuable than being able to derive the attention equation from memory. The math becomes most useful when you need to diagnose failures, optimize systems, or go beyond out-of-the-box solutions.
Sunil Kumar Sahu 11:33 AM  
I think ReLU is best choice for hidden layers?
Academic_Lead_SM 11:52 AM 
ReLU is often a very good choice for hidden layers, but not always the best choice.

ReLU is simple, fast, and works well in many deep neural networks.
GELU is commonly preferred in modern Transformers because it provides smoother activations.
Tanh is often used in RNNs/LSTMs because it helps represent memory with positive and negative values.

So, a better statement would be:

ReLU is a popular and effective activation function for many hidden layers, but the best choice depends on the architecture and task.
Kavya Srinivasan 11:33 AM  
How are we getting the other contexts fro the word? For example: If beetle as an insect is what is read in sentence, from where are the contexts of car and music band is being fetched? 
Academic_Lead_SM 11:40 AM 
The model does not fetch the meanings from the sentence. It learns multiple possible meanings during training. When it sees a word like "beetle", the surrounding words provide context and help the model choose the correct meaning. For example, "crawled on a leaf" suggests the insect, while "drove a Beetle" suggests the car. Attention helps the model focus on the relevant context.
Vinod Krishnan 11:34 AM  
in this example too, 
xi as beetle if W1 is created dynamically how does the matrix know beetle is some percentage of bird, insect, car, etc?
Academic_Lead_SM 11:58 AM 
The key point is that W
1
	​

 does not know what "beetle" means by itself. The knowledge comes from training.

Initially, the embeddings and weight matrices are random. During training, the model repeatedly sees sentences containing words like beetle, insect, bird, and car. Over time, backpropagation adjusts the weights so that words appearing in similar contexts get similar representations.

As a result, the embedding for "beetle" may end up close to concepts related to insects, while being farther from unrelated concepts. If the word has multiple meanings, the surrounding context helps the model emphasize the correct interpretation.

So the matrix does not contain a hand-written rule such as:

beetle = 70% insect, 20% car, 10% something else

Instead, these relationships emerge automatically from the training data through learned embeddings and attention patterns.
Abhishek Singh 11:34 AM  
What would have happened if instead of expanding the dimension and then reducing it after applying Relu, I just apply Relu for non-linearity after the attention layer, then also it should work right..??
Academic_Lead_SM 11:40 AM 
Yes, it would work, but it would usually be less powerful. ReLU adds non-linearity, but the expand → ReLU/GELU → reduce feed-forward block gives the model a larger space to learn richer feature interactions. So direct ReLU is possible, but expansion improves capacity and performance.
Payal Sengupta 11:34 AM  
what enables this second layer expansion happens?
Academic_Lead_SM 11:47 AM 
The expansion happens because a learned weight matrix transforms the representation into a higher-dimensional space. This gives the model more capacity to learn complex patterns.
Sweta Kumari 11:38 AM  
How this information is going to help us building enterprise RAG, building Agentic AI use cases, deploying them, govern them? more than 80% of the class has lost interest in this course, don't you think you should pay attention on this instead just keep going on slides?
Academic_Lead_SM 11:42 AM 
This is a valid concern. While concepts like RNNs, LSTMs, attention, and Transformers may seem theoretical, they help explain why LLMs, RAG systems, and AI agents behave the way they do. Understanding embeddings, attention, context windows, and model limitations is useful when designing RAG pipelines, managing agent memory, debugging hallucinations, and evaluating system performance. However, for learners focused on enterprise AI, it is equally important to connect these fundamentals to practical topics such as RAG architecture, agent workflows, deployment, monitoring, security, governance, and cost optimization. A balance between theory and real-world implementation is usually the most effective approach.
Deepak Kumar 11:39 AM  
In transformer models , if the output is not desirable , then what needs to be fixed?

Like there is a famous response from claude regarding Car wash question ?
Academic_Lead_SM 11:42 AM 
If a Transformer gives a poor output, the issue is usually not the architecture itself. Common causes are bad prompts, missing context, poor training data, retrieval errors (RAG), or alignment issues. In practice, we fix this by improving prompts, providing better context, fine-tuning, or improving the retrieval and feedback mechanisms.
Abhishek Singh 11:43 AM  
Yes, got it, So RElu add only non-linearity but increasing dimension means now we have more wider space to map the input to output..thanks!
Academic_Lead_SM 11:44 AM 
Yess you are right and thanks
Jasleen Kaur 11:44 AM  
as per program calender today topics were context window, decoding, metrics but we didnt covered it, we only did rnn, lstm and attention. when will it cover, bcoz from next seesion it shows models and apis will be covered
Academic_Lead_SB 11:46 AM 
The topic of the session in the listed agenda was listed as RNN, Transformers and attention. We will delve deep inside the transformer archchitecture further in the next lecture. API will be covered in the later lectures.
Ravi prasad Reddy Soda (You) 11:44 AM  
is positional encoding highlighting the position and order of important words that are important for attention?
Academic_Lead_SM 11:45 AM 
Not exactly. Positional encoding does not identify important words. Its job is to tell the model where each token appears in the sequence and what its order is.

The attention mechanism decides which words are important, while positional encoding provides the order information needed to distinguish sentences such as:

"Dog bites man"
"Man bites dog"

So:

Positional encoding = position and order

Attention = importance and relevance
Pushkaraj Shingre 11:45 AM  
how positional encoding values are calculated for each token? is there any method for it
Academic_Lead_SB 11:47 AM 
prof is explaining
Srushti Anant Shimpi 11:46 AM  
Since self-attention is permutation-invariant, the original Transformer relies on positional encodings to capture sequence order. Do you think the model's understanding of order is fundamentally different from how RNNs encode order through recurrence, and could this affect generalization to much longer sequences than seen during training?
Academic_Lead_SM 11:46 AM 
Yes. There are two common approaches:

Fixed positional encoding – The original Transformer uses mathematical sine and cosine functions to generate a unique position vector for each token position (1st, 2nd, 3rd, etc.).
Learned positional encoding – Modern models often learn positional embeddings during training, just like word embeddings.
Ravi prasad Reddy Soda (You) 11:46 AM  Dismissed by host
Thank you !
Anil Kumar 11:47 AM  
There is a mix of self-attention and cross-attention in transformer model described today for machine translation. But today's popular LLMs are decoder only. Is there any difference between loss function in this transformer vs decoder only transformer?
Chandan Kumar_TA 11:56 AM 
No, the core loss function is the same in both cases.
Traditional Encoder-Decoder Transformer are generally used in translation
Decoder-only Transformer are generally used in next token prediction/generation.

Ravi prasad Reddy Soda (You) 11:49 AM  
In a commercial LLM model what is the number of multi-head attention used?
Chandan Kumar_TA 11:51 AM 
Small models - Usually 16 to 32 attention heads per layer.
Medium models- Usually 32 to 64 attention heads.
Large models- Often 64 to 128+ heads per layer 
Ravi prasad Reddy Soda (You) 11:50 AM  
means the number of multi heads used ? and is there a priority list of relationships they look for ?
Academic_Lead_SM 11:53 AM 
Yes, multi-head attention means multiple attention heads are used in parallel, and each head can learn to focus on different types of relationships.
Anonymous attendee 11:50 AM  
How is todays class will be useful for future practical implementation?
Academic_Lead_SM 11:50 AM 
Yess this will lead to transformers implementations
Abhishek Singh 11:50 AM  
Why onoly limited to sin and cosine for positional encoding, we could use sigmoid, tanh also, they are also limited in range. Sim=goid goes from 0 to 1 and tanh goes from -1 to 1. Why partiality towards sin and cosine only.
Academic_Lead_SM 11:51 AM 
Sine and cosine are used because they provide unique, repeating patterns that encode both absolute and relative positions. Nearby positions get similar encodings, while distant positions get different ones in a predictable way. Sigmoid and tanh quickly saturate (become almost constant), making it difficult to distinguish between many different positions. Therefore, sine and cosine preserve positional information much more effectively. Please go through Attention is all you need paper
Manish Kumar 11:50 AM  
I want to understand how semantic is being decided by the model? When to select the word “it “ to Animal and  when to pick “Street”?
Academic_Lead_SM 11:52 AM 
The model learns semantics from training data, not from hand-written rules. When it sees a word like "it", attention compares it with other words in the sentence and assigns higher weights to words that make grammatical and semantic sense.

For example:

"The animal didn't cross the street because it was tired."

The model learns that "tired" is more likely to describe an animal than a street, so attention gives more weight to "animal". Over millions of training examples, the model learns these patterns and uses them to decide which word a pronoun like "it" most likely refers to.
Abhishek Singh 11:54 AM  
Got it, basically if we can use any trignometric function as longs as it is periodic, limited in range and also doesn't saturate quickly. Sin and cosine are one such functions there can be others also
Academic_Lead_SM 11:56 AM 
Yes, that's the right. The key properties are that the function should provide distinct positional patterns, be bounded, and avoid quick saturation so that different positions remain distinguishable.

Sine and cosine became the standard choice because they are simple, periodic, smooth, and allow the model to infer relative positions naturally. In principle, other periodic functions could also be used, but sine and cosine have been found to work well and have useful mathematical properties for encoding position.
Academic_Lead_SM 12:01 PM 
Rotary Positional Embeddings in LLAMA is another example PE
Biswanath 11:55 AM  
how does the ff network using relu make the vec space richer?
Chandan Kumar_TA 12:00 PM 
The FFN with ReLU makes the vector space richer by adding non-linearity and increasing model capacity at each position.
The FFN works position-wise on each token independently. It first projects the vector to a much higher dimension (x times larger), applies ReLU which introduces non-linearity by zeroing out negative values, and then projects it back to the original dimension.
sauvik garai 11:55 AM  
Real life example of positional encoing ?
Academic_Lead_SB 11:56 AM 
token system in a doctors clininc.... :)
Pushkaraj Shingre 11:57 AM  
output of encoder is then used in decoder in cross attention layer?
Academic_Lead_SM 11:58 AM 
Yes. In an encoder–decoder Transformer, the encoder's output is passed to the decoder's cross-attention layer.

The encoder processes the source sentence and produces contextual representations.
In the decoder, cross-attention allows each target token to look at these encoder representations.
This helps the decoder focus on the relevant parts of the source sentence while generating the output.

So:

Encoder output → Cross-Attention → Decoder.
Manish Kumar 11:57 AM  
What is the reason for expanding 4 fold and again bring it back. 
is there any specific rule that 4 fold will always work in all scenarios?
Chandan Kumar_TA 12:03 PM 
The 4x expansion in the feed-forward network comes from the original Transformer paper. There is no strict mathematical rule that 4x will always be optimal. It was an empirical choice.
The reason for expanding and then compressing back is to create a temporary higher-dimensional space where the non-linear activation (ReLU) can learn more complex transformations. In the higher dimension, the model has more room to separate features and create richer representations before projecting back to the original dimension.
Ravi prasad Reddy Soda (You) 11:59 AM  
are there different types of attention ?

Ravi prasad Reddy Soda (You) 11:59 AM 
are there different types of attention ?
Academic_Lead_SM 12:06 PM 
Yes. There are several types of attention used in deep learning:

Self-Attention – a token attends to other tokens in the same sequence (used in Transformers).
Cross-Attention – one sequence attends to another sequence (e.g., decoder attending to encoder output in translation).
Masked Self-Attention – prevents a token from seeing future tokens (used in GPT-like models).
Multi-Head Attention – multiple attention mechanisms run in parallel, each learning different relationships.


Abdeali Dodiya 12:00 PM  
TBH, the lectures should have a better balance between theory and practical implementation. We are spending a lot of time understanding the concepts and formulas but there is very little focus on how to implement them in real world scenarios. Practical exercises hands-on labs & end-to-end examples would help us understand how these concepts are actually used.
Academic_Lead_SM 12:04 PM 
We have hands on session after this QNA
Abhishek Singh 12:02 PM 
Got it thanks!
Academic_Lead_SM 12:03 PM 
Thanks




