# Code 3.0
## Stages of programs
- Code 1.0: Humans write all the logic by hand using traditional programming.
- Code 2.0: AI learns the logic from data using models like neural networks.
- **Code 3.0**: AI systems improve themselves through self-learning and adaptation.

## Code 3.0 program
A Code 3.0 program using LLMs means:
  The program uses the LLM to write, critique, and refine its own code or behavior — with minimal human input.

It’s like combining:
- LLM (e.g., GPT-4) as a programmer
- A loop or agent framework to evaluate and revise
- Optionally, memory or database to retain learnings over time

Build steps:
- Step 1: Define the goal
- Step 2: Feedback loop
    ```
      loop:
        generate_code_or_plan()
        execute_or_simulate()
        evaluate_result()
        revise_code_or_plan()
    ```
- Step 3: Use LLM to Power the Cycle
    - Generate initial solution
    - Reflect and critique its own output
    - Try a revised version
- Step 4: Add Memory (Optional but powerful).
    - Use: A vector database (e.g., Chroma, Weaviate), JSON or SQLite
    - To store: Past attempts, Lessons learned, Evaluation scores

Example Use Case: Self-Improving Code Generator
- User: "Write a Python script that scrapes prices from a website."
- LLM writes first version.
- Script runs, fails.
- LLM is shown the error and rewrites the code.
- Each attempt is logged and used to fine-tune future decisions.

## Code 3.0 framework
Code 3.0 framework helps you to build Code 3.0 program, coordinate with other Code 3.0 programs to build a complete solution for you business needs.


