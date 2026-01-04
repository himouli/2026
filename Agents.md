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
   
  
