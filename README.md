# Email Subject Line Generator 📧  
*(LLM Engineering – Week 1 Day 1)*

This repo contains my solution for **Week 1 Day 1** of the *LLM Engineering* course.

The goal is simple:

> **Given the body of an email, generate a short, clear, human-like subject line using an LLM.**

---

## 🔍 What this project does

- Reads an email body (plain text).
- Sends it to an OpenAI chat model with a **system prompt** that says:
  > “You are an agent who reads the email and suggests the appropriate short subject line.”
- The model returns a **single subject line**, e.g.:

> `Reminder: Deployment & Regression Test Deadline for Medicaid Mapping`

This is the kind of feature you might build into a **commercial email tool** to help users auto-generate subject lines.

---

## 🧠 Key ideas used

Inside `day1.ipynb`:

1. **System prompt**  
   Tells the model its role and the exact task (read email → output subject only).

2. **Messages list**  
   - `system`: instructions for the model  
   - `user`: the email body text  

3. **OpenAI Chat Completion call**  
   Calls a small, fast model (`gpt-4.1-mini` or `gpt-4.1-nano`) to generate the subject.

4. **Output**  
   Prints only `response.choices[0].message.content`, which is the subject line.

---

## ▶️ How to run this notebook

1. **Clone the repo**

   ```bash
   git clone https://github.com/karnemanideep/email-subject-generator.git
   cd email-subject-generator
