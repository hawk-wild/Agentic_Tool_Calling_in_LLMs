# Agentic_Tool_Calling_in_LLMs
How enabling tool calls affects task success on problems requiring complex computation.
This is a mock research project.
The link to the research paper:  
https://github.com/hawk-wild/Agentic_Tool_Calling_in_LLMs/blob/main/Agentic_Tool_Calliing_Research.pdf


🧮 Agentic Tool Calling in LLMs: Enhancing Math Reasoning with a Calculator AgentProject OverviewThis repository contains the implementation and experimental code for the research paper, "Agentic Tool Calling in LLMs: Enhancing Math Reasoning with a Calculator Agent."The project investigates the performance limitations of smaller Large Language Models (LLMs) on complex numerical reasoning tasks (like the GSM8K benchmark) and proposes a dynamic Agentic Tool-Calling System to overcome these limitations. We demonstrate that while the model's abstract reasoning is strong, its failure lies in deterministic numerical execution, a gap which an external calculator tool fills effectively.🚀 Key FeaturesCore Model: Uses the Meta LLaMa 3.1 8B Base Model as the central reasoning engine.Tool Integration: Implements a robust, safe Python-based calculator tool for deterministic computation.Protocol: Employs a ReAct-style (Reasoning and Acting) framework and a custom <CALC>...</CALC> communication protocol to manage tool calls within the model's chain of thought.Two-Phase Strategy: Utilizes a Plan-and-Execute methodology to ensure the model structures complex, multi-step problems before performing calculations.📈 Experimental Results (Summary)The experiments confirm the significant value of tool augmentation, showing that the LLM's primary failure in math is execution, not conceptual thought.ExperimentModel VariantDatasetTool UseAccuracy (%)Performance GainBaselineLLaMa 3.1 8B BaseGSM8KCoT Only15%-ReAct AgentLLaMa 3.1 8B BaseGSM8KTool-Augmented50%+35% AbsoluteDirect CallLLaMa 3.1 8B BaseCustom MathTool-Augmented80%+32% (vs. 48% CoT)🛠️ Repository Structureagent_tool_loop.py: Python script containing the core run_agent_plan_and_execute loop (Cell 4).protocol.py: Defines the PLANNING_PREFIX and EXECUTION_PREFIX and history building functions (Cell 3).safe_calculator.py: The deterministic, safe expression evaluator (Cell 2).data/: Placeholder for the GSM8K and Custom Math Datasets used for evaluation.notebooks/: Jupyter notebooks used for initial prototyping and visualization of results.💻 Setup and UsagePrerequisites:Python 3.10+PyTorchHugging Face Transformers (transformers)SentencePiece (for LLaMa tokenization)Installation:# Clone the repository
git clone [https://github.com/YourUsername/agentic-tool-calling-llm.git](https://github.com/YourUsername/agentic-tool-calling-llm.git)
cd agentic-tool-calling-llm

# Install dependencies
pip install -r requirements.txt
Running the Agent:The main entry point is designed to interface with the LLaMa 3.1 8B model loaded via the Hugging Face library.from agent_tool_loop import run_agent_plan_and_execute
# ... (Load model and tokenizer here)

question = "A train covers 360 km in 4 hours. Another train goes at 3/4 of this speed. How much time will the second train take to travel 270 km?"
result = run_agent_plan_and_execute(question, model, tokenizer)

print(f"Final Answer: {result['final_answer']}")
