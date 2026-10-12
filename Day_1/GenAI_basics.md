# Lecture 01 — Introduction to Generative AI

**Series:** Complete GenAI with Python & LangChain  
**Topic:** What is GenAI? ML vs DL vs GenAI, LLM / LIM / LVM / LAM, and why learn GenAI in 2026  
**Type:** Theory / Orientation (No code yet)

## Table of Contents

1. Why This Series?
2. What Is Generative AI?
3. Traditional AI vs Modern AI
4. Machine Learning — Netflix Example
5. Deep Learning — Face Unlock Example
6. Generative AI — ChatGPT Example
7. Family of Large Models (LLM, LIM, LVM, LAM)
8. Why Learn GenAI in 2026?
9. Quick Revision Summary

## 1. Why This Series?

In the last two years, many GenAI products have launched:

- **ChatGPT** (OpenAI)
- **Gemini** (Google)
- **Claude** (Anthropic)
- **ElevenLabs** (Voice and audio)
- **Grok** (xAI)
- And many more

**Industry Trends:**

- Almost every company is adopting AI.
- AI skills are appearing in nearly every job discussion.
- Students are building AI-powered projects.
- Developers integrate AI to improve productivity.

**Common Questions This Lecture Answers:**

- What is GenAI?
- How is it different from ML and DL?
- What is the difference between Traditional AI and GenAI?
- Why learn GenAI now, in 2026?

## 2. What Is Generative AI?

**Definition:** Generative AI is a technology or system that creates new content based on a user's query or prompt.

### Key Points

- It does not simply retrieve a fixed, pre-written answer.
- It generates a response based on the input prompt.
- The same prompt can produce different responses.
- Content is not limited to text; it can include images, videos, audio, and code.

| Content Type | Examples |
|---|---|
| Text | Answers, essays, emails |
| Images | AI art, edited photos |
| Videos | Short clips generated from prompts |
| Audio | Voice, music, speech |
| Code | Programs, scripts |

Because it generates new content, it is called **Generative AI**.

## 3. Traditional AI vs Modern AI

```text
              Artificial Intelligence
                       |
             +---------+---------+
             |                   |
       Traditional AI        Generative AI
          (ML + DL)          (Content Creation)
             |                   |
      Predicts or             Generates new
      recognizes data            content
```

| Category | Traditional AI | Generative AI |
|---|---|---|
| Includes | Machine Learning and Deep Learning | Large language models and image, video, and audio generation models |
| Main purpose | Predicts or recognizes patterns from data | Generates new content |
| Output | Labels, scores, recommendations | Text, images, videos, audio, code |
| Examples | Netflix recommendations, face unlock | ChatGPT, Gemini, Claude |

## 4. Machine Learning — Netflix Example

**Scenario:** You watch action, thriller, and comedy movies regularly on Netflix. After some time, Netflix starts suggesting movies you might like.

### How Does It Work?

Netflix uses information about your viewing activity, such as:

- Movie title and description
- Release year
- Genre
- How long you watched a title
- Other viewing and interaction signals

Based on your past behavior and preferences, the machine learning model predicts what you might enjoy watching next.

```text
Past Watch History
        |
        v
Machine Learning Model Learns Patterns
        |
        v
Predicts New Recommendations
```

**Definition:** Machine Learning (ML) enables machines to learn patterns from data and use them to make predictions or decisions without explicitly programming every rule.

## 5. Deep Learning — Face Unlock Example

**Scenario:** Unlocking a phone using facial recognition.

### Setup Phase

The system learns facial features using images or other training data. Depending on the device, it may use specialized sensors to capture facial information.

### Unlock Phase

The phone attempts to recognize you under different conditions, such as:

- Wearing a cap
- Wearing glasses
- Different lighting conditions

### How Does It Work?

The system learns complex patterns and features, including:

- Shape and position of the eyes
- Structure of the nose
- Overall facial geometry
- Other distinguishing facial features

**Definition:** Deep Learning (DL) is a subset of machine learning that uses neural networks with multiple layers to learn complex patterns from data.

## 6. Generative AI — ChatGPT Example

Ask ChatGPT: "What is GenAI in short?"

It generates a short answer based on your prompt. If you select "Try again," it may produce a different answer to the same question.

This demonstrates generative behavior: the model produces an answer rather than simply selecting a single fixed response from a list of pre-written answers.

### What Runs Behind ChatGPT, Gemini, and Claude?

**LLM — Large Language Model**

Large language models are trained on large amounts of text and other data, depending on the model. They can understand and generate text and perform tasks such as summarization, question answering, and code generation.

## 7. Family of Large Models

| Abbreviation | Full Form | Main Capability | Example |
|---|---|---|---|
| LLM | Large Language Model | Text understanding and generation | ChatGPT, Gemini, Claude |
| LIM | Large Image Model | Image generation | Google's Nano Banana |
| LVM | Large Vision Model | Image and visual content understanding; some models also support video | Google's Veo is primarily a video-generation model |
| LAM | Large Audio Model | Audio understanding and generation | Audio and voice-generation models |

**Note:** These abbreviations are not all standardized across the AI industry. Their meanings can vary by context. Veo is specifically known as a video-generation model, while vision models may focus on interpreting visual information.

### Homework

Think about practical use cases for large audio models:

- Speech and voice generation
- Text-to-speech
- Music generation
- Voice cloning
- Speech recognition
- Audio transcription

## 8. Why Learn GenAI in 2026?

GenAI is an important and rapidly developing area of technology, with applications across software development, education, business, research, and other industries.

### Skill Development Perspective

| Today | Coming Years |
|---|---|
| GenAI can provide an additional advantage | GenAI skills may become increasingly important in many roles |
| Knowing GenAI can help differentiate your profile | Employers may increasingly expect familiarity with AI tools and workflows |
| Developers use AI to improve productivity | Developers may increasingly build AI-powered applications |

Learning GenAI can help you:

- Build AI-powered applications.
- Integrate language models into software.
- Develop chatbots and AI agents.
- Work with frameworks such as Python and LangChain.
- Strengthen your portfolio through practical projects.

The series aims to cover at least 10 projects, providing opportunities to practice and demonstrate your skills.

## 9. Quick Revision Summary

- **Generative AI:** Generates new content, such as text, images, videos, audio, and code, based on prompts.
- **Traditional AI:** Often focuses on prediction, classification, and recognition.
- **Machine Learning:** Learns patterns from data to make predictions or decisions. Example: Netflix recommendations.
- **Deep Learning:** Uses multilayer neural networks to learn complex patterns. Example: facial recognition.
- **LLM:** Large Language Model, primarily associated with language understanding and generation.
- **LIM:** Large Image Model, a term used for image-generation models in some contexts.
- **LVM:** Large Vision Model, generally associated with visual understanding; terminology varies.
- **LAM:** Large Audio Model, associated with audio understanding and generation.
- **Generative Behavior:** The same prompt can produce different outputs.
- **Career Relevance:** GenAI knowledge can help developers build modern AI-powered applications.

### Key Takeaway

Traditional AI often predicts or recognizes patterns, while Generative AI creates new content. Understanding this distinction is the foundation for learning GenAI with Python and LangChain.
