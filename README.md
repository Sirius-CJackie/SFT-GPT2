## Reprogramming Large Language Models for Spatia-Temporal Traffic Flow Forecasting
# The framework of STF-GPT2
![The framework of STF-GPT2 ](framework.png)

# Dataset
| **Dataset**             | **CitiBike**             | **NYCTaxi**              |
|:------------------------|:------------------------:|-------------------------:|
| **Total**               | 2.6 million              | 35 million               |
| **Number of Nodes**     | 250                      | 266                      |
| **Time Span**           | 01/04/2016 - 30/06/2016  | 01/04/2016 - 30/06/2016  |
| **Timestep**            | 30 minutes               | 30 minutes               |
| **Number of Timesteps** | 4368                     | 4368                     |

# Setup
Before training, please configure the following training dictio￾nary:
config = {
"file_dir": "CitiBike_dataset/bike_pick/",
"epochs": 300,
"num_nodes": 250,
"lrate": 1e-3,
"batch_size": 64,
"input_dim": 3,
"clip": 5.0,
"es_patience": 100,
"input_len": 12,
"output_len": 12,
"wdecay": 0.0001,
"save": "./",
}

• file_dir: set the path to the dataset folder (either CitiBike_dataset or NYCTaxi_dataset).
• epochs: number of training epochs.
• num_nodes: number of spatial IDs in the dataset (250 for CitiBike, 266 for NYCTaxi).
• lrate: learning rate.
• batch_size: batch size, default is 64.
• input_dim: number of input features, default is 3.
• clip: gradient clipping norm, default is 5.0.
• es_patience: early stopping patience, training stops if no improvement is observed
for 100 epochs.
• input_len: input series length.
• output_len: prediction series length.
• wdecay: weight decay coefficient for regularization.
• save: directory to save output files.
