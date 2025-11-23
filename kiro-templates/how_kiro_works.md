# How Kiro Works

Kiro is an AI assistant that helps you build features systematically through a structured spec-driven development process.

## Core Philosophy

Instead of jumping straight into code, Kiro guides you through three phases:
1. **Requirements** - What needs to be built
2. **Design** - How it will be built  
3. **Tasks** - Step-by-step implementation plan

This ensures every feature is well-planned before implementation begins.

## The Spec Structure

Each feature gets its own folder in `.kiro/specs/{feature-name}/` containing:

- `requirements.md` - User stories and acceptance criteria
- `design.md` - Technical architecture and implementation approach
- `tasks.md` - Actionable coding checklist

## Workflow Process

### Phase 1: Requirements Gathering
- I create initial requirements based on your feature idea
- Uses user stories format: "As a [role], I want [feature], so that [benefit]"
- Includes acceptance criteria in EARS format (Easy Approach to Requirements Syntax)
- Example: "WHEN user clicks submit THEN system SHALL validate all fields"
- We iterate until you approve the requirements

### Phase 2: Design Documentation  
- I research and create a comprehensive design.md
- Covers architecture, components, data models, error handling, testing strategy
- May include Mermaid diagrams for visual representation
- Addresses all requirements from the previous phase
- We iterate until you approve the design

### Phase 3: Task Planning
- I break down the design into actionable coding tasks in tasks.md
- Creates numbered checklist items (1.1, 1.2, etc.)
- Each task references specific requirements
- Focuses only on code implementation activities
- Prioritizes incremental, testable progress
- We iterate until you approve the task list

## Key Features

- **Iterative Approval** - You must explicitly approve each document before moving to the next
- **Requirement Traceability** - Tasks link back to specific requirements
- **Incremental Development** - Tasks build on each other progressively
- **Code-Focused** - Tasks only include activities a coding agent can execute

## Task Execution

Once your spec is complete, you can execute tasks by:
- Opening the `tasks.md` file
- Clicking "Start task" next to individual task items
- I'll implement one task at a time, stopping for your review between tasks

## Getting Started

To begin a new feature spec, simply describe your idea and I'll guide you through the three-phase process. For existing specs, I can help review, update any phase, or execute implementation tasks as needed.