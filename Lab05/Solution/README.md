In this folder, i have provided two main files: main-wandb.py and main.py

main-wandb.py attempts runs a sweep using wandb by trying out combinations of different learning rates, batch sizes, optimizers, and a few different hidden layer structures.
main.py uses the most promising configuration found in the above step and trains a model for more epochs.

So far, the best configuration I have found is this:
learning_rate = 0.0026704041957093883
training_batch_size = 128
optimizer_name = 'adam'
hidden_layers = [512, 256, 128]

Training a model using this configuration over 120 epochs, yielded a final validation accuracy of 0.5302. Tha vlidation accuracy stabilizes at around 0.53 at cca. epoch 70, and slightly fluctuates from there while never reaching more than 0.54.
This can be seen at: https://wandb.ai/radu-solca/Advanced-Topics-in-Neural-Networks-Template-2023-lab05_Solution?workspace=user-radu-solca

Runs from the sweep can be seen at: https://wandb.ai/radu-solca/RN.LAB5?workspace=user-radu-solca

The run I used to get the hyper parameters for the longer training session: https://wandb.ai/radu-solca/RN.LAB5/runs/xonn57ee?workspace=user-radu-solca

Further possible improvements to hyper paramater tuning method:
- Use fewer generations during sweep to get faster results.
- Study the chart of top X attempts to get hints of what could be improved. (e.g. lyric-sweep-17 seems to have a lot of oscilation)

Based on the above, I would expect 6 points for this homework:
1p Implement the logging system using Tensorboard.
1p Use weights & biases to hyper-tune your parameters.
1p Evaluate SGD and Adam.
1p Evaluate RMSProp, AdaGrad.
1p Find a configuration which achieves over 40% validation accuracy
1p Find a configuration which achieves over 50% validation accuracy

NOTE: SAM was attempted, but due to time constraints, it was removed as it caused too many issues. I chose to focus instead to find a good configuration using the other optimizers.