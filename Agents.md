== Notes from Master AI Agent Engineering - Build Autonomous AI Agents Ed Donner (Udemy) ==
Week 1:

- AI agents are programs where LLM outputs control the workflow
- In practice , it describes an AI solution that involves any or all of these
  -- Multiple LLM calls
  -- LLM with ability to use tools
  -- An environment where LLMs interact
  -- A planner to co-ordinate activities

  Agentic Systems
   - Workflows are systems where LLMs and tools are orchestrated through pre-defined code paths
   - Agents are systems where LLMs dynamically direct their own processes and tool usage,
     maintaining control over how they accomplish tasks.

Workflow Design Patterns:

1. Prompt Chaining
   Input  ---> LLM 1 ---> Gate (code) --- LLM 2 --> LLM 3 ---> Ouput
   Decompose into fixed tasks

2. Routing
   Direct an input into a specialized subtask ensuring separation of concerns
   Input ---> LLM Router ----> LLM1 , LLM2 , LLM 3 ----->  Output

3. Parallelization
   Breaking down tasks and running multiple subtasks concurrently
   Input --> [ Coordinator (code) ] ---> LLM 1, LLM 2, LLM3 ----> [ Aggregator (code) ] ---> Output

4. Orchestrator
   Complex tasks are broken down dynamically and combined
   Input -> [ Orchestrator ] --> LLM 1, LLM 2, LLM 3 -> [ Synthesizer ] ---> Output

5. Evaluator-Optimizer
   LLM output is validated by another
   Input -> LLM Generator ----> LLM Evaluator --> Output

Agents vs Workflow Pattern in LLM Application Design

Agents are :
    - Open Ended
    - Feedback loops
    - No fixed path

Human --> LLM Call --> Environment

Risks of Agent Framework :
 - Unpredictable Path
 - Unpredictable Output
 - Unpredictable Cost
 - Monitor
 - Guardrail

Agentic AI frameworks
             - No frameworks
             - MCP Model Context Protocol
             - OpenAI Agents SDK
             - CrewAI
             - LangGraph
             - AutoGen

  Resources vs Tools
   - We can provide an LLM with resources to improve its expertise
   - Basically this just means showing data relevant to the question into the prompt
   - RAG

  Tools:
    - Give the LLM the power to carry out actions like (i) Query the database or message other LLMs

  An LLM responds with the actions needed , and the code is executed on the local machine. 

  System Prompt : Overall instruction to set the context
  User Prompt : Actual question from user

  
   
