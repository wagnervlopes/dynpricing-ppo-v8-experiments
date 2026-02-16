# DynPricing PPO V8 Experiments

Reproducible experimental framework for dynamic pricing in retail using Deep Reinforcement Learning (Proximal Policy Optimization – PPO) with temporal demand modeling.

This repository contains the final experimental configuration (V8) used in the Master's dissertation:

**"Dynamic Pricing in Retail: A Reinforcement Learning Approach"**

---

## 1. Dataset

The dataset used in this experiment is publicly available and versioned with DOI:

https://doi.org/10.5281/zenodo.18664650

The dataset repository contains:

- Processed chronological splits (train/validation/test)
- Canonical preprocessing pipeline
- Schema definition
- Integrity verification (MD5 checksums)

---

## 2. Repository Structure

configs/ Final hyperparameter configuration (PPO V8)
envs/ Environment implementation (MDP formulation)
scripts/ Training and evaluation scripts
results/v8/ Final experimental outputs


---

## 3. Experimental Configuration (V8)

The V8 configuration represents the final tuned model used in the dissertation.

Main characteristics:

- PPO (Stable-Baselines3)
- Continuous action space (price adjustments)
- Temporal demand modeling
- Evaluation against economic baseline policies
- Identical environment across PPO and baselines

Key files:

- `configs/ppo_tuned_v8.yaml`
- `results/v8/config_used.yaml`
- `results/v8/command.txt`

---

## 4. Reproducing the Experiment

### Step 1 – Install dependencies

pip install -r requirements.txt


### Step 2 – Train PPO V8

python scripts/train_ppo_sb3_v8.py


### Step 3 – Run baseline policies

python scripts/run_baselines_v8.py


### Step 4 – Compare PPO vs baselines

python scripts/compare_ppo_vs_baselines_v8.py


---

## 5. Final Results

The final experimental results are stored in:

- `results/v8/ppo_summary.csv`
- `results/v8/comparison_ppo_baselines.csv`
- `results/v8/best_model.zip`

The PPO V8 model achieved superior performance relative to baseline pricing policies under identical environmental conditions.

---

## 6. Reproducibility Notes

- Chronological data split (no temporal leakage)
- Training-only normalization (no information leakage)
- Fixed configuration file
- Explicit command log (`command.txt`)
- Versioned dataset (DOI)
- Versioned experiment (Git tag v1.0.0)

---

## 7. License

This code is released for academic and research purposes.

