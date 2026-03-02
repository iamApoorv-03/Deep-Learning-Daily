Deep Learning Foundations — From Scratch to Mini-Batch Training
📌 Overview

This repository documents my structured journey of building Deep Learning foundations from scratch using PyTorch.

Instead of copying models blindly, the goal of this project is:

Understand optimization mathematically

Build models step-by-step

Experiment with noise, bias–variance, and overfitting

Implement professional training pipelines

This repository evolves daily as part of a disciplined coding practice.

🧱 Phase 1 — Linear Regression From Scratch
Concepts Covered

Gradient Descent (GD)

Learning rate behavior

Loss function (Mean Squared Error)

requires_grad=True

loss.backward()

Manual parameter updates

Zeroing gradients

Key Learnings

High learning rate → overshooting minima

Low learning rate → slow convergence

Gradient computation via autograd

Optimization stability depends on scaling

📈 Phase 2 — Noise & Bias–Variance Tradeoff
Experiments

Added Gaussian noise to dataset

Observed effect on:

Loss

Learned parameters

Model stability

Key Learnings

Increasing noise increases irreducible error

Loss increases even if model is correct

Overfitting happens when model memorizes noise

Generalization gap = Train loss − Eval loss

🧮 Phase 3 — Polynomial Regression
Experiments

Added polynomial features (x²)

Observed training instability

Implemented feature normalization

Key Learnings

Feature scaling is critical for stability

Without normalization, gradients explode

Learning rate interacts with feature magnitude

Optimization geometry matters

🧠 Phase 4 — Neural Networks
Model Used
nn.Sequential(
    nn.Linear(1, hidden_units),
    nn.ReLU(),
    nn.Linear(hidden_units, 1)
)
Concepts Covered

ReLU non-linearity

Model capacity

Train/test split

model.train() vs model.eval()

torch.no_grad()

Sorting for clean visualization

Key Learnings

ReLU introduces piecewise linear behavior

Larger models increase variance

Normalizing inputs and outputs improves training

Evaluation must be separated from training

📦 Phase 5 — Mini-Batch Training with DataLoader
Implemented

TensorDataset

DataLoader

Mini-batch Gradient Descent

Average loss tracking per epoch

Key Learnings

Batch training introduces gradient noise

Average loss is more meaningful than total loss

Batch size affects convergence stability

Professional training requires structured pipeline

🛡 Phase 6 — Regularization
Techniques Tested

L2 Regularization (Weight Decay)

Dropout

Observations

For simple regression dataset:

Base model generalized well

Regularization slightly increased bias

Regularization helps when:

Model capacity >> data complexity

Key Insight

Regularization reduces variance but increases bias.

It is useful only when overfitting is present.

📊 Phase 7 — Overfitting Experiments
Experiments

Reduced training samples

Increased model size (512-512 architecture)

Increased noise magnitude

Observations

Small data + large model → overfitting

Large noise + high capacity → memorization

Evaluation loss reveals generalization failure

🚀 Phase 8 — Professional Training Enhancements (Current Phase)
Implemented

Mini-batch training

Train/Eval separation

Loss tracking

Learning curve plotting

Early stopping logic

Why This Matters

This transforms toy scripts into production-style pipelines.

📂 Repository Structure

linear_regression_scratch.py

polynomial_regression.py

neural_network_basic.py

nn_train_test_split.py

nn_l2_dropout.py

nn_minibatch_dataloader.py

🎯 Current Level

After completing these phases, I now understand:

Optimization mechanics

Model capacity & generalization

Bias–variance tradeoff

Regularization behavior

Mini-batch training dynamics

Training stability

Overfitting diagnosis

This repository reflects structured daily improvement toward intermediate-level deep learning proficiency.

📅 Ongoing Plan

Batch size experiments

Early stopping improvements

Optimizer comparisons (SGD vs Adam)

Learning rate scheduling

Model checkpointing
