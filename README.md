DynPricing PPO V8 Experiments

Reproducible experimental framework for dynamic pricing in retail environments using Deep Reinforcement Learning (Proximal Policy Optimization – PPO) with temporal demand modeling.

This repository contains the frozen experimental configuration (V8) corresponding to the final validated results presented in the Master's dissertation:

Dynamic Pricing in Retail: A Reinforcement Learning Approach.

Persistent Identifiers (DOI)

To ensure full scientific reproducibility and long-term archival preservation, both data and code are versioned and publicly archived via Zenodo.

Dataset (processed data, splits, preprocessing pipeline):
https://doi.org/10.5281/zenodo.18664650

Experimental Code (this repository – PPO V8 framework):
https://doi.org/10.5281/zenodo.18664856

Both DOIs correspond to immutable releases and guarantee traceability of the exact experimental configuration used in the dissertation.

1. Scientific Context

Dynamic pricing in retail constitutes a sequential decision-making problem under uncertainty, where pricing actions influence future demand and revenue trajectories.

The problem is formalized as a Markov Decision Process (MDP), in which:

The state space includes historical demand information, economic context variables, and pricing signals.

The action space corresponds to continuous price adjustments.

The reward function reflects cumulative revenue performance.

The transition dynamics are induced by the empirical retail dataset.

The PPO V8 configuration represents the final tuned policy validated against multiple baseline pricing strategies under identical environmental conditions.

2. Repository Structure

configs/ – Final hyperparameter configuration (PPO V8)
envs/ – MDP environment implementation
scripts/ – Training and evaluation pipeline
results/v8/ – Frozen experimental outputs (final results)

Key files include:

configs/ppo_tuned_v8.yaml – Final PPO hyperparameters

configs/calib.json – Calibration parameters

envs/simple_price_env_v8.py – Environment (MDP) definition

scripts/train_ppo_sb3_v8.py – PPO training script

scripts/run_baselines_v8.py – Baseline evaluation

scripts/compare_ppo_vs_baselines_v8.py – Comparative evaluation

results/v8/ppo_summary.csv – Final performance metrics

results/v8/comparison_ppo_baselines.csv – PPO vs baseline comparison

results/v8/best_model.zip – Frozen trained PPO model

results/v8/config_used.yaml – Exact configuration used

results/v8/command.txt – Execution command log

3. Experimental Configuration (V8)

The V8 configuration corresponds to the final validated experimental setup.

Core characteristics:

Algorithm: Proximal Policy Optimization (Stable-Baselines3 implementation)

Continuous action space for price adjustments

Chronological data split (train / validation / test)

No temporal leakage

Identical evaluation environment across PPO and baselines

Frozen hyperparameter configuration

Explicit execution log

This version represents the definitive experimental state associated with the dissertation validation.

4. ## Baseline Policies

For comparative evaluation, deterministic and heuristic baseline policies were implemented within the same MDP structure used by PPO.

Let the pricing problem be defined as:

M = (S, A, P, R, γ)

where S is the state space, A the continuous action space (price adjustments), P the transition dynamics, R the revenue-based reward function, and γ the discount factor.

The PPO agent learns a policy πθ(a|s), while baseline policies are fixed mappings:

π⁽ⁱ⁾ : S → A

The following baselines were evaluated:

- Constant Price Policy: aₜ = 0  
- Fixed Markup Policy: pₜ = pₜ₋₁(1 + δ)  
- Monthly DIEESE 1% Policy: pₜ = pₜ₋₁(1.01)  
- Realistic Adjustment Band Policy  

All policies were evaluated under identical environment dynamics, reward structure, and chronological data splits to ensure structural fairness.

5. Reproducibility Protocol

Step 1 – Install dependencies:

pip install -r requirements.txt

Step 2 – Train PPO V8:

python scripts/train_ppo_sb3_v8.py

Step 3 – Evaluate baseline policies:

python scripts/run_baselines_v8.py

Step 4 – Generate comparative analysis:

python scripts/compare_ppo_vs_baselines_v8.py

The resulting artifacts should match the contents stored in results/v8/.

6. Final Experimental Results

The final validated outputs are available in:

results/v8/ppo_summary.csv

results/v8/comparison_ppo_baselines.csv

results/v8/best_model.zip

The PPO V8 agent demonstrated superior cumulative revenue performance relative to multiple economically grounded baseline pricing strategies under identical MDP conditions.

7. Methodological Integrity

The experimental protocol adheres to the following principles:

Strict chronological partitioning

Training-only normalization

Fixed hyperparameter configuration

Identical evaluation environment across policies

Explicit command logging

Immutable versioning via Git tags

Archival via Zenodo DOI

These elements ensure scientific reproducibility, transparency, and auditability.

8. License

This repository is made available for academic and research purposes. Refer to the LICENSE file for specific terms of use.

Citation

If this work contributes to academic research, please cite both the dataset and the experimental framework using their respective DOIs.
