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

 * Vibe Coding Best Practices
   - Good Vibes - Prompt Well - Ask for short answers and latest APIs for todays data
   - Vibe but verify -- Ask 2 LLMs the same question
   - Step up the vibe --ask to break down your request into independently testable steps
   - Vibe and Validate - ask an LLM then get another LLM to check
   - Vibe with Variety - ask for 3 solutions to the same problem, pick the best
  
  Week 3 

  Crew AI - Enterprise, UI studio, OpenSource Framework
  Crew AI Crews - Autonomous solutions with AI teams of Agents with diff roles
  Crew AI Flows - Structured automations by dividing complex tasks into precise workflows

  Agent - Unit with an LLM, a role, a goal, a backstory, memory, tools
  Task - a specific assignment to be carried out
  Crew - a team of agents and tasks
  YAML configuration - @agent @tasks @crew


  Week 4 
     Langgraph - Langraph studio Langgraph Platform
     Agent workflows represented as graphs
     State represents the current snapshot of the application
     Nodes : are python functions that represent agent logic
     Edges : python functions that determine what Node to execute next based on state, they can be conditional or fixed
     Nodes do the work, edges choose what to do next

  5 steps to building the Graph 
    1. Define the state class
    2. Start the Graph Builder
    3. Create a Node
    4. Create the Edges
    5. Compile the Graph


    Week 6 : MCP
        1. A framework for  building agents
        2. A fundamental change to how agents work 
        3. A way to code agents
        4. Protocol - a standard
        5. A simple way to integrate tools, resources, prompts

    Host : 
    MCP Client 
    MCP Server 
    MCP Client ---stdio --- MCP Server [ Local ]
    MCP Client --- SSE --- MCP Server [ Remote ]
    
  
   
