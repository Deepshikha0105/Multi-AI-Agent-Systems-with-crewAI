# Multi-Agent Blog Generation using CrewAI

## Overview
This project uses CrewAI to create an automated blog writing workflow using multiple AI agents.

The workflow contains:
1. Content Planner
2. Content Writer
3. Editor

Each agent performs a specific task to generate a final blog article.

---

# Workflow

Topic Input → Planner Agent → Writer Agent → Editor Agent → Final Blog Output

---

# Agents

## 1. Planner Agent
### Role
Content Planner

### Purpose
- Research the topic
- Find trends and news
- Identify target audience
- Create content outline
- Suggest SEO keywords

---

## 2. Writer Agent
### Role
Content Writer

### Purpose
- Write complete blog article
- Use planner output
- Create introduction, body, and conclusion
- Add SEO keywords naturally
- Format article in markdown

---

## 3. Editor Agent
### Role
Editor

### Purpose
- Proofread article
- Fix grammar issues
- Improve writing quality
- Ensure professional tone

---

# Main Components

## Agent
Defines AI personality and responsibilities.

Example:
```python
planner = Agent(...)
```

---

## Task
Defines work assigned to an agent.

Example:
```python
plan = Task(...)
```

---

## Crew
Combines agents and tasks into a workflow.

Example:
```python
crew = Crew(
    agents=[planner, writer, editor],
    tasks=[plan, write, edit]
)
```

---

# Execution

The workflow starts using:

```python
result = crew.kickoff(inputs={"topic": "Artificial Intelligence"})
```

---

# Output

The final result is:
- A complete markdown blog article
- Generated automatically using AI agents

Save output into markdown file:

```python
with open("blog_output.md", "w", encoding="utf-8") as f:
    f.write(str(result))
```

---

# Technologies Used

- Python
- CrewAI
- OpenAI API
- Multi-Agent AI System

---

# Conclusion

This project demonstrates how multiple AI agents can collaborate to automate blog generation using CrewAI.
