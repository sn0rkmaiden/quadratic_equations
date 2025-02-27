# :world_map: Heatmap of attention maps

## :rocket: Goal of the study:
To detect patterns of attention in the trained model.

## :trophy: Motivation

The attention mechanism is an extremely common method in modern deep learning models, which allows not only to improve the performance of neural machine translation applications, but also, using, for example, the Transformer model, to increase the speed of training. Currently, the relevance of the problem of studying the capabilities and improving the efficiency of this model is increasing, and therefore, in this paper, we propose to consider in detail how this model consistently solves the problem using the example of solving quadratic equations.

## :books: Problem statement and research methodology

The task was to train the T5 model from the Hugging Face library and then interpret and visualize attention patterns. From the input sequence, consisting of a string representation of a quadratic equation, it is necessary to obtain the solution and answer to this equation.

 - Input: $7x^2+3556x+451612=0$
 - Output: $D=(3556^2-47451612)=0;x=(-3556-0)/(27)=-254;x=(-3556+0)/(27)=-254;x=-254;x=-254;$

T5 model is trained from scratch on the generated dataset of 100,000 examples and their solutions in the form of a detailed description of obtaining the discriminant and roots of the equation.

In total, there are 50% equations with two solutions, 30% with one solution, and the remaining 20% are ​​without solutions.

The training and testing data is divided in a ratio of 80 to 20.

After the fine-tuning procedure, various modifications of viewing attention maps should be considered to identify hypotheses.
Conduct an analysis of the map of each head on each individual layer, which show the importance of specific operations of the input, output sequences and their interrelation. Use the averaged attention maps for statistics, namely, which operations were used most often. And obtain the so-called summary map: number of layers * number of input tokens, which shows the importance of each token on each layer for all heads.

![Example of visualization](https://github.com/sn0rkmaiden/quadratic_equations/blob/main/visualize_attention.jpg)
