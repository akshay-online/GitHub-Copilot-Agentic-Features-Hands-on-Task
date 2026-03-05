# GitHub Copilot Agentic Features – Hands-on Task

## Objective

Build a small **API Log Performance Analyzer** using GitHub Copilot by leveraging:

* Copilot Instructions
* Copilot Prompts
* Copilot Skills
* Custom Agent

Time limit: **15 minutes**

---

# Scenario

Your organization runs several microservices. Recently, the platform team noticed that some APIs are responding slowly.

You need to quickly build a **tool that analyzes API logs and identifies slow endpoints**.

The logs contain the following fields:

* endpoint
* response_time
* status_code
* timestamp

Example log:

```json
[
  {
    "endpoint": "/orders",
    "response_time": 1800,
    "status_code": 200,
    "timestamp": "2026-01-10T10:22:31"
  },
  {
    "endpoint": "/products",
    "response_time": 1200,
    "status_code": 500,
    "timestamp": "2026-01-10T10:22:35"
  }
]
```

---

# Task 1 – Configure Copilot Instructions

Create a file:

```
.github/copilot-instructions.md
```

Add the following instructions:

```
You are an expert backend engineer.

Follow these standards:
- Use Python FastAPI
- Follow modular coding practices
- Add logging and error handling
- Write reusable functions
- Add docstrings
- Generate pytest unit tests
```

This ensures Copilot generates **consistent and structured code**.

---

# Task 2 – Use a Copilot Prompt to Generate the Application

Create a file called:

```
app.py
```

Use Copilot Chat and prompt:

```
Create a FastAPI service that reads API logs from a JSON file.

Each log contains:
endpoint
response_time
status_code
timestamp

The API should provide the following endpoints:

1. /slow-endpoints
   Return the top 5 slowest endpoints.

2. /average-response
   Return average response time per endpoint.

3. /error-rate
   Return endpoints where error rate is greater than 5%.

Use clean architecture and add logging.
```

Let Copilot generate the application.

---

# Task 3 – Create Copilot Skills

Create a file called:

```
skills.md
```

Define the following skills.

### Skill 1 – Log Analyzer

```
Skill: Analyze API logs

Input:
JSON API logs

Output:
- Top slow endpoints
- Average response time per endpoint
- Error rate
```

### Skill 2 – Performance Recommendation

```
Skill: API Performance Advisor

Analyze slow APIs and suggest optimizations.

Recommendations should include:
- caching
- async processing
- database optimization
- indexing strategies
```

Use Copilot Chat and ask it to **apply these skills to your generated code**.

---

# Task 4 – Create a Custom Agent

Create a file:

```
agent.md
```

Define a **Performance Engineer Agent**.

```
Agent Name: API Performance Engineer

Responsibilities:
- Analyze API logs
- Identify slow endpoints
- Suggest performance improvements
- Recommend monitoring metrics
```

Now ask the agent:

```
Analyze the API logs and provide:

1. Top slow endpoints
2. Possible bottlenecks
3. Performance improvements
4. Metrics that should be monitored
```

---

# Expected Output

By the end of the exercise you should have:

* A FastAPI application
* Log analysis endpoints
* Copilot instructions configured
* Skills defined
* A custom agent performing analysis

---

# Bonus Challenge (Optional)

Ask Copilot to extend the application with:

* A dashboard endpoint
* A CSV report of slow APIs
* Prometheus metrics for monitoring
