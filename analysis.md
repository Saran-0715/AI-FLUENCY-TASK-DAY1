# Agentic AI: Foundations and Open-Source Practice — Day 1

## 1. Scenario

### College Course Fee Assistant

For this task, I selected a college course-fee scenario using three course codes:

- CS101 — Rs. 12,000
- AI202 — Rs. 18,000
- DS303 — Rs. 15,000

The same course-fee questions were tested using three different approaches:

1. Plain Chatbot
2. Rule-Based Workflow
3. AI Agent

The purpose was to understand the difference between an LLM-based chatbot, a predefined rule-based system, and an AI agent that combines an LLM, tools, and a loop.

---

# 2. Explanation of Each Approach

## 2.1 Plain Chatbot

The plain chatbot mainly uses an LLM to generate responses to the user's questions. It does not use the private course-fee data stored in the Python program, and it does not have access to the course-fee lookup tool or calculator tool.

The chatbot receives a question and sends it to the LLM with a simple system instruction. The LLM then generates a response based on the information available to it.

In my scenario, the chatbot was asked questions such as:

- What is the fee for AI202?
- What is the total fee for CS101 and AI202 after a 10% scholarship?
- Is DS303 more expensive than CS101, and by how much?
- Write a two-line welcome message for new AI students.

The chatbot could answer general questions and generate a welcome message, but it could not reliably access the private course-fee information. For example, instead of directly giving the stored fee for AI202, it asked for additional information about the course and institution.

This shows that a plain chatbot can produce fluent and confident responses but cannot automatically access private application data unless that data is explicitly provided to it through an appropriate mechanism.

### Limitations

The main limitations of the plain chatbot in this scenario are:

- It does not directly access the private course-fee dictionary.
- It cannot verify course fees using a tool.
- It may not reliably perform multi-step calculations using private data.
- Its answers depend mainly on the LLM's generated response.

---

## 2.2 Rule-Based Workflow

The rule-based workflow does not use an LLM. Instead, it follows predefined programming rules and conditions.

In this project, the workflow uses the course-fee data stored in the Python program. It identifies course codes such as CS101, AI202, and DS303 and applies predefined rules to answer supported questions.

For example, when asked for the fee of AI202, the workflow can look up AI202 in the course-fee data and return Rs. 18,000.

It can also handle a predefined total-fee calculation and a scholarship percentage when the question matches the rules that were programmed.

However, the workflow cannot dynamically understand every type of question. In the challenge question asking which two courses can be taken within a Rs. 30,000 budget, the workflow returned that it could only answer questions about course fees because no rule had been created for that type of request.

### Limitations

The main limitations of the rule-based workflow are:

- It depends on predefined rules.
- New types of questions require additional programming.
- It does not reason dynamically about an unfamiliar task.
- It cannot automatically select tools based on the user's request.
- Its flexibility is limited by the conditions implemented by the developer.

---

## 2.3 AI Agent

The AI agent combines an LLM, tools, and a loop.

In this project, the agent has access to two tools:

1. `get_course_fee` — retrieves the fee for a course code.
2. `calculator` — performs arithmetic calculations.

The agent receives the user's question and the LLM decides whether a tool is required. If a tool is required, the agent calls the appropriate tool, observes the result, and sends that result back to the LLM. The process continues until the agent can provide a final answer.

For example, for the question:

"What is the total fee for CS101 and AI202 after a 10% scholarship?"

the agent used the course-fee tool to retrieve the fees:

- CS101 → Rs. 12,000
- AI202 → Rs. 18,000

It then used the calculator tool to calculate the discounted total:

Rs. 30,000 × 0.9 = Rs. 27,000

The agent then generated the final answer.

The agent also handled the challenge question:

"I can pay Rs. 30,000. Which two courses can I take together within this budget?"

It identified the possible combinations and found:

- CS101 + AI202 = Rs. 30,000
- CS101 + DS303 = Rs. 27,000

This demonstrates how an AI agent can use tools and multiple steps to handle a task that was not directly supported by the fixed workflow rules.

### Limitations

The AI agent also has limitations:

- It depends on the availability and correct implementation of its tools.
- The LLM may still make incorrect decisions about which tools to use.
- Tool calls and model responses can fail.
- The agent requires more implementation than a simple chatbot or fixed workflow.
- More complex tasks may require additional tools and safeguards.

---

# 3. Comparison Table

| Basis for comparison | Plain chatbot | Rule-based workflow | AI agent |
|---|---|---|---|
| Flexibility | Flexible in generating natural-language responses, but cannot directly access the private course-fee data | Limited to predefined rules and supported question patterns | Flexible because the LLM can decide how to use available tools |
| Decision-making | Generates an answer using the LLM | Follows predefined conditions | LLM decides which tool to use and what action to take next |
| Tool usage | No tools used | Uses programmed logic but no LLM tool-calling loop | Uses `get_course_fee` and `calculator` tools |
| Private-data access | Cannot directly access the private course-fee data | Directly accesses the stored course-fee data | Accesses the private data through the course-fee tool |
| Multi-step task handling | Limited and may not reliably use private data for multiple steps | Only handles multi-step tasks that were explicitly programmed | Can perform multiple tool calls and continue until the task is completed |
| Automation | Generates responses but has limited task automation | Automates predefined operations | Can dynamically select tools and perform multiple actions |
| Reliability | Can produce fluent but unverified answers | Reliable for cases covered by its predefined rules | Can provide reliable results when the tools and instructions are correctly implemented |

---

# 4. Suitability Analysis

For the selected college course-fee scenario, the AI agent is the most suitable approach when the task requires flexible questions, access to private course-fee data, calculations, and multiple steps.

The plain chatbot is useful when the main requirement is generating or explaining natural-language responses. However, it does not directly access the private course-fee data used in this project.

The rule-based workflow is useful when the questions and required operations are predictable. It can directly use the stored course-fee data and provide reliable results for the rules that have been programmed. However, its capabilities become limited when the user asks a new type of question that was not included in the rules.

The AI agent is suitable when the user can ask different types of questions and the system needs to select and use tools dynamically. In this project, the agent used the course-fee tool to retrieve private data and the calculator tool to perform arithmetic. It also handled the budget challenge by considering multiple course combinations.

Therefore, for this particular scenario, an AI agent provides the flexibility needed to combine private-data access, tool usage, decision-making, and multi-step task handling.

---

# 5. Conclusion

A plain chatbot, rule-based workflow, and AI agent solve problems in different ways.

A plain chatbot is appropriate when the main requirement is natural-language conversation, explanation, brainstorming, or generating responses using an LLM.

A rule-based workflow is appropriate when the problem is predictable and the required steps and conditions can be clearly defined in advance. It can provide consistent results for the cases covered by its rules.

An AI agent is appropriate when a problem requires an LLM to interact with tools, access application data, perform multiple steps, observe results, and continue working toward a final answer.

The key difference demonstrated by this project is:

**Plain Chatbot = LLM**

**Rule-Based Workflow = Predefined Rules**

**AI Agent = LLM + Tools + Loop**

The college course-fee scenario demonstrates that an AI agent can combine language understanding with programmatic tools to handle more flexible and multi-step tasks.