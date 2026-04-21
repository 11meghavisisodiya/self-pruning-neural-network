INTRODUCTION:

Neural networks have achieved remarkable success across various domains, but their increasing size and
complexity make them computationally expensive to deploy. Large models require significant memory,
storage, and processing power, which limits their usability in real-world applications, especially on
resource-constrained devices.
To address this challenge, model compression techniques such as pruning are commonly used to reduce
the number of parameters. Traditional pruning methods are typically applied after training, where less
important weights are removed in a separate step.
In this project, we explore a more efficient approach by integrating pruning directly into the training
process. The proposed method enables the neural network to learn which connections are unnecessary
and remove them dynamically, resulting in a more compact and efficient model.

Problem Statement:

The objective of this case study is to design and implement a neural network capable of self-pruning
during the training process. Traditional pruning methods are applied after model training and require
additional steps to remove less important parameters. In this problem, each weight in the network is
associated with a learnable gate parameter that controls its importance. These gates determine whether
a connection should remain active or be effectively removed. The challenge is to develop a training
mechanism that encourages unnecessary weights to be pruned automatically while maintaining strong
classification performance. This requires designing a custom neural network architecture along with a loss
function that balances prediction accuracy and model sparsity, enabling the network to dynamically
optimize its own structure

Results Table:


Lambda      Test Accuracy           Sparsity (%)
0.001          54.04%                   0.07%
0.01            53.03%                  0.08%
0.1             52.89%                  0.08%
<img width="983" height="640" alt="Graph" src="https://github.com/user-attachments/assets/300eb970-01e8-4667-99bb-ddd3c385d991" />



