# RL_MLDL_2425 – Reinforcement Learning Project

This repository contains the full implementation of **Project 4 – Reinforcement Learning** for the *MLDL 2024/25* course at Politecnico di Torino. It includes both:

- The six official tasks required by the project (REINFORCE, Actor-Critic, PPO, UDR)
- A custom project extension based on **Multi-Agent DDPG (MADDPG)** using both UDR and ensemble with distilled policies in a cooperative setting.

---

## Repository Structure

```
RL_MLDL_2425/
├── Tasks/                         
│   ├── REINFORCE/                 
│   │   ├── env/
│   │   ├── agent.py
│   │   └── train.py
│   ├── Actor_Critic/             
│   │   ├── env/
│   │   ├── agent.py
│   │   └── train.py
│   └── PPO/                      
│       ├── env/
│       └── train_sb3.py
│
├── MADDPG/                        
│   ├── Distill.py
│   ├── GlobalAgent.py
│   ├── MADDPG.py
│   ├── MultiAgent.py
│   ├── Networks.py
│   ├── Train.py
│   ├── test.py
│   ├── Tuning.py
│   ├── main.py
│   ├── RL_Multi_Agent/            
│   ├── tuning_results/            
│   ├── vmas/                      
│   └── wandb/                     
│
├── RL_Multi_Agent.pdf
├── README.md
└── requirements.txt
```

---

## Official Tasks (in `/Tasks/`)

These follow the structure and requirements described in the official project guidelines:

| Task | Description |
|------|-------------|
| **1** | Explore the MuJoCo Hopper environment |
| **2** | Implement REINFORCE (with/without baseline) |
| **3** | Implement Actor-Critic from scratch |
| **4** | Implement PPO using Stable-Baselines3 |
| **5** | Evaluate sim-to-sim transfer (source→target) |
| **6** | Uniform Domain Randomization (UDR) for Hopper |

Run REINFORCE:

```bash
cd Tasks/REINFORCE
python train.py
```

Run Actor-Critic:

```bash
cd Tasks/Actor_Critic
python train.py
```

Run PPO:
```bash
cd Tasks/PPO
python train_sb3.py --algo ppo --domain source
```

⸻

## Project Extension – Multi-Agent MADDPG

In the `MADDPG/` folder you will find a custom extension implementing:
- Multi-Agent Deep Deterministic Policy Gradient (MADDPG)
- Centralized critic and decentralized actors
- Ensemble learning: multiple policies per agent
- Policy distillation into compact deployable policies
- Uniform Domain Randomization (UDR) to enhance robustness
- Tested in the VMAS `Balance` cooperative environment

Run MADDPG training:

```bash
cd MADDPG
python Train.py --env_name Balance --n_agents 2 --n_episodes 1000000
```

⸻

## Highlights
- From-scratch implementation of REINFORCE and Actor-Critic
- Use of SB3 to train PPO and SAC
- Sim-to-sim transfer testing (source vs. target domain)
- Uniform Domain Randomization on Hopper dynamics
- Multi-agent coordination with MADDPG
- Robustness via policy ensembles and distillation
- Integration with Weights & Biases (wandb)

⸻

## Authors

| Name                              | Student ID     | Email                          | Department                    |
|-----------------------------------|----------------|--------------------------------|-------------------------------|
| Francesco Mastrosimone            | s348159        | s348159@studenti.polito.it     | DAUIN – Politecnico di Torino |
| Brian Facundo Condorpocco Morales | s346581        | s346581@studenti.polito.it     | DAUIN – Politecnico di Torino |
| Salvatore Nocita                  | s346378        | s346378@studenti.polito.it     | DAUIN – Politecnico di Torino |
| Luciano Scarpino                  | s346205        | s346205@studenti.polito.it     | DAUIN – Politecnico di Torino |

---

## Third-Party Licenses

This repository makes use of the [Vectorized Multi-Agent Simulator (VMAS)](https://github.com/proroklab/VectorizedMultiAgentSimulator) developed by the Multi-Agent & Heterogeneous Systems Lab (Prorok Lab), University of Cambridge.

VMAS is licensed under the **MIT License**.  
© 2022 Prorok Lab.

> Permission is hereby granted, free of charge, to any person obtaining a copy  
> of this software and associated documentation files (the "Software"), to deal  
> in the Software without restriction, including without limitation the rights  
> to use, copy, modify, merge, publish, distribute, sublicense, and/or sell  
> copies of the Software, and to permit persons to whom the Software is  
> furnished to do so, subject to the following conditions: [...]

Full license available [here](https://github.com/proroklab/VectorizedMultiAgentSimulator/blob/main/LICENSE).

## Documentation

- [RL_Multi_Agent.pdf](RL_Multi_Agent.pdf) — Project report with theory, methods, and results.

The report includes:
- Background on Reinforcement Learning methods (REINFORCE, Actor-Critic, PPO, MADDPG)
- Implementation details (environments, agents, training loops)
- Distillation and ensemble logic
- Experimental setup and tuning results
- Analysis and discussion
