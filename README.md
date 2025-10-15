# 🧮 Agentic Tool Calling in LLMs: Enhancing Math Reasoning with a Calculator Agent

## Project Overview
This repository contains the implementation and experimental code for the research paper, **"Agentic Tool Calling in LLMs: Enhancing Math Reasoning with a Calculator Agent."** 

The project investigates the performance limitations of smaller Large Language Models (LLMs) on complex numerical reasoning tasks (like the **GSM8K** benchmark) and proposes a dynamic **Agentic Tool-Calling System** to overcome these limitations. We demonstrate that while the model's abstract reasoning is strong, its failure lies in deterministic numerical execution, a gap which an external calculator tool fills effectively.

## Key Features
* **Core Model:** Uses the **Meta LLaMa 3.1 8B Base Model** as the central reasoning engine.
* **Tool Integration:** Implements a robust, safe, AST-parsed Python calculator tool for deterministic, secure computation.
* **Protocol:** Employs a **ReAct-style (Reasoning and Acting)** framework and a custom <CALC>...</CALC> communication protocol to manage tool calls within the model's chain of thought.
* **Two-Phase Strategy:** Utilizes a Plan-and-Execute methodology to ensure the model structures complex, multi-step problems before performing calculations.

## 📈 Experimental Results (Summary)
The experiments confirm the significant value of tool augmentation, showing that the LLM's primary failure in math is execution, not conceptual thought.


Note: The experiments and the results are in the notebook. This is a mock research just for learning purpose. [The link to the research paper](https://github.com/hawk-wild/Agentic_Tool_Calling_in_LLMs/blob/main/Agentic_Tool_Calliing_Research.pdf)

