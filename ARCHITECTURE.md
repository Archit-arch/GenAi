# AI Operations Assistant: Multi-Agent Architecture (Python)

## Folder Structure
```
.
├── agents/
│   ├── __init__.py
│   ├── planner.py
│   ├── executor.py
│   └── verifier.py
├── core/
│   ├── __init__.py
│   ├── orchestration.py
│   ├── message_bus.py
│   └── state.py
├── tools/
│   ├── __init__.py
│   ├── registry.py
│   └── implementations/
│       ├── __init__.py
│       ├── system.py
│       └── external.py
├── schemas/
│   ├── __init__.py
│   └── planner_steps.schema.json
├── configs/
│   └── settings.yaml
└── scripts/
    └── run_assistant.py
```

## Responsibilities
- `agents/planner.py`: Produces a JSON plan of steps for the task, including inputs, dependencies, and expected outputs.
- `agents/executor.py`: Executes the plan by calling registered tools and recording results.
- `agents/verifier.py`: Validates that the plan execution is complete, consistent, and meets success criteria.
- `core/orchestration.py`: Coordinates agent interactions, sequencing, retries, and termination.
- `core/message_bus.py`: Standardizes inter-agent message formats and routing.
- `core/state.py`: Maintains shared state, task context, and execution artifacts.
- `tools/registry.py`: Central registry for tool discovery, validation, and invocation.
- `tools/implementations/`: Concrete tool adapters (system, external APIs, integrations).
- `schemas/planner_steps.schema.json`: JSON schema for planner output validation.
- `configs/settings.yaml`: Configuration for agent behavior, tool limits, and runtime options.
- `scripts/run_assistant.py`: Entry point to initialize and run the assistant.
