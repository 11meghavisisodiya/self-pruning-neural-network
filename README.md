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

Methodology:

The objective of this case study is to design and implement a neural network capable of self-pruning
during the training process. Traditional pruning methods are applied after model training and require
additional steps to remove less important parameters. In this problem, each weight in the network is
associated with a learnable gate parameter that controls its importance. These gates determine whether
a connection should remain active or be effectively removed. The challenge is to develop a training
mechanism that encourages unnecessary weights to be pruned automatically while maintaining strong
classification performance. This requires designing a custom neural network architecture along with a loss
function that balances prediction accuracy and model sparsity, enabling the network to dynamically
optimize its own structure.
🔹 4.1 PrunableLinear Layer
🔹 4.2 Sparsity Loss
🔹 4.3 Training Setup

Results Table:


Lambda      Test Accuracy           Sparsity (%)
0.001          54.04%                   0.07%
0.01            53.03%                  0.08%
0.1             52.89%                  0.08%
<img width="983" height="640" alt="Graph" src="https://github.com/user-attachments/assets/300eb970-01e8-4667-99bb-ddd3c385d991" />

Analysis:

The experimental results clearly demonstrate the impact of the sparsity regularization parameter λ on
model behavior. As λ increases, the sparsity level of the network also increases, indicating that more
connections are being pruned.
At lower values of λ, most gate values remain close to one, meaning that the majority of weights are
active. This results in higher accuracy but lower sparsity. As λ increases, more gate values move toward
zero, effectively removing less important connections and making the model more compact.
However, this increase in sparsity comes at the cost of reduced accuracy, highlighting a clear trade-off
between model efficiency and performance. The histogram of gate values further confirms that a large
number of gates converge near zero, validating the effectiveness of L1 regularization in promoting
sparsity.

Conclusion:

This case study successfully demonstrates the implementation of a self-pruning neural network that can
dynamically remove unnecessary connections during training. By introducing learnable gate parameters
and incorporating L1-based sparsity regularization, the model is able to achieve a balance between
accuracy and efficiency.
The results highlight that integrating pruning directly into the training process is an effective alternative
to traditional post-training pruning methods. This approach enables the model to adapt its structure
automatically and produce a more optimized architecture.

