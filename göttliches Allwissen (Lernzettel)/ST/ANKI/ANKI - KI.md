TARGET DECK: ST::KI

Unterschied: RAG vs. Tool Calls bzg. Kontext #flashcard
- RAG: Was das Modell als Kontext bekommt wird von einem separaten Entscheider bestimmt
- Tool Calls: Modell bestimmt durch MCP-aufrufe selbst, was es als Tool-Output in den Kontext laden will $\to$ geschlossener Kreis. **ReAct**
<!--ID: 1793805339689-->


4 pillars of SASE: #flashcard
1. Actors
2. Processes
3. Artifacts
4. Tools
<!--ID: 1793805339696-->



Pillar 1 of SASE: Actors: #flashcard
- human role: oversight & coordination
- AI roles: Agents for
	- requirements
	- code-generation
	- review
<!--ID: 1793805339702-->


Pillar 2 of SASE: Processes #flashcard
Typical Process
1. Briefing Script
2. Agent Loop
3. Consultation Request Pack
4. Merge Readiness Pack
<!--ID: 1793805339710-->


Pillar 3 of SASE: Artifacts #flashcard
- Briefing Script
- Mentor Script
	- general guidelines: coding standards, conventions, ...
- Consultation Request Pack
- Merge Readiness Pack
<!--ID: 1793805339722-->


	
Pillar 4 of SASE: Tools #flashcard
Two distinct environments:
Agent Command Env. :
- human interaction
- Mission brief
Agent Execution Env:
- Tool Calls
- Build processes
- Testing 
<!--ID: 1793805339726-->


Definition: Agentic Harness #flashcard
An Agentic Harness is an environment that wraps an LLM with tools, context management, and an execution loop, enabling it to autonomously complete multi-step software engineering tasks.
<!--ID: 1793805339731-->


3 forms of technical debt: #flashcard
1. technical debt: code, bad architecture, implementations
2. cognitive debt: system too complex for team to understand it
3. intent debt: bad documentation of what the goal, constraints, ... even are
<!--ID: 1793805339736-->


Vibe Coding vs Agentic Engineering:  #flashcard
Agentic Engineering:
	User knows what they are doing and puts in place proper oversight, review, tests, planning.
Vibe Coding:
	Unsupervised and unreviewed. Just let the LLM do stuff.
	Good for quick prototypes.
<!--ID: 1793805339743-->


