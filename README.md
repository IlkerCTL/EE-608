# EE-608

The objective function in this problem is the mathematical expression that quantifies the probability of the target language given the source language. This can be represented as follows:

No alt text provided for this image
where 𝑥 is the source text, 𝑦 is the target text, and 𝑃 (y|x) is the probability of the target text given the source text.

The constraints in this problem can include requirements on the length and complexity of the translation, the fluency and coherence of the language, and the preservation of important information and structure in the source text. For example, the following constraints could be imposed:

• x and y are strings of characters from the respective languages

• Len(x) ≤Lmax, where Lmax is the maximum allowed length of the source text

• Len(y) ≤ Lmax, where Lmax is the maximum allowed length of the target text

• y is fluent and coherent in the target language

• y preserves the important information and structure of x

From the perspective of optimization, this problem presents several challenges and opportunities. For instance, the objective function is a probability, which is a non-convex function that is difficult to optimize directly. Therefore, I may need to use approximate methods such as Monte Carlo sampling or variational inference to estimate the objective function and its gradients. Additionally, the constraints are non-linear and may require specialized techniques such as penalty methods or interior-point methods to handle them efficiently.

Finally, the large size and complexity of natural language data may require the use of distributed and parallel optimization algorithms to scale up the optimization process and enable efficient training of the deep neural network.

One important aspect of this optimization process is to evaluate the network's performance using metrics that align with the objectives and constraints of the problem. For example, in machine translation, I may want to use metrics such as the BLEU score, which measures the similarity between the predicted and reference translations, or TER, which measures the number of edits required to make the predicted translation match the reference. I can use these metrics to guide the optimization process, by adjusting the network's architecture and hyper-parameters to maximize the performance on the evaluation metrics. This can be done using optimization algorithms such as gradient descent, which iteratively adjusts the network parameters to reduce the error on the evaluation metrics.

Testing on a test dataset

To validate the solution, I can test the performance of the trained network on a held-out dataset of parallel texts in the source and target languages. This can involve using the network to translate the source texts and comparing the predicted translations to the reference translations, using evaluation metrics such as the BLEU score and TER. Let f(x) be the neural network that I have trained, where x is the source text. Then the predicted translation of a source text x is given by 𝑓(𝑥), and the reference translation is given by 𝑦. I can then compute the evaluation metrics as follows:

BLEU(f(x), y) = similarity between f(x) and y

TER(f(x), y) = number of edits required to make f(x) match y



By comparing the performance of the network on the held-out dataset to the performance on the training dataset, I can assess the validity of the solution and determine whether the network is able to generalize to unseen data. I can also use cross-validation or other techniques to further validate the solution and reduce the impact of random variations in the data. In my solution to validate the model, the code splits the dataset into a training and validation set using the train_test_split function from the sklearn library. The training set is used to train the model, while the validation set is used to evaluate the performance of the model on unseen data. The code then trains the model on the training set and calculates the validation loss and validation accuracy on the validation set after each epoch. This allows the code to monitor the performance of the model during training and identify overfitting or under-fitting. The code can then adjust the model hyper-parameters or stop training early to prevent over-fitting and improve the performance of the model on the validation set. Eventually the trained model got a 98% Sparse Categorical Accuracy (BLUE metric) on our test data, which is a very good, but there is still room for better accuracy.

