# Prompt Engineering Module

## Overview

This module covers the fundamentals and advanced techniques of prompt engineering - the art and science of crafting effective inputs for Large Language Models (LLMs).

## What You'll Learn

### Prompt Engineering Fundamentals
- **Basic Prompts**: Simple text completions and continuations
- **Zero-Shot Prompting**: Performing tasks without examples
- **One-Shot Prompting**: Learning from a single example
- **Few-Shot Prompting**: Multiple examples for pattern establishment

### Advanced Techniques
- **Chain-of-Thought (CoT)**: Step-by-step reasoning approaches
- **Self-Consistency**: Multiple solution paths and verification

### Practical Applications
- **Text Summarization**: Condensing content effectively
- **Question Answering**: Building QA systems
- **Text Classification**: Categorizing text automatically
- **Code Generation**: Generating code from descriptions
- **Role Playing**: Task-specific chatbots

## Notebook Contents

**File**: `In-Context Learning and Prompt Templates for Advanced AI.ipynb`

This comprehensive notebook includes:
- 45-60 minutes of content
- Multiple examples for each technique
- Hands-on exercises with TODO sections
- LangChain integration patterns
- Real-world use cases
- Best practices and tips

## Getting Started

### 1. Prerequisites
- Python 3.8+
- Jupyter Notebook/Lab installed
- An LLM provider account (IBM Watsonx, OpenAI, Claude, etc.)

### 2. Install Dependencies
```bash
pip install -r ../../requirements.txt
```

### 3. Configure LLM
In the notebook, you'll find a section to configure your LLM. Update with your provider:

```python
# Example: IBM Watsonx
from langchain_ibm import WatsonxLLM

llm = WatsonxLLM(
    model_id="ibm/granite-4-h-small",
    url="YOUR_WATSONX_URL",
    project_id="YOUR_PROJECT_ID",
    params={
        "max_new_tokens": 256,
        "temperature": 0.5,
    }
)
```

### 4. Run the Notebook
```bash
jupyter notebook "In-Context Learning and Prompt Templates for Advanced AI.ipynb"
```

## Key Concepts Explained

### Temperature Parameter
- **Low (0.1-0.3)**: More focused, deterministic, factual responses
- **Medium (0.4-0.6)**: Balanced creativity and consistency
- **High (0.7-1.0)**: More creative, diverse, unpredictable outputs

### Top-P (Nucleus Sampling)
- **Low (0.1-0.3)**: Conservative, focused vocabulary
- **High (0.7-0.9)**: More diverse vocabulary and ideas

### Top-K
- **1**: Greedy decoding (always picks most likely token)
- **40-50+**: More varied outputs with multiple token choices

### Max Tokens
- Controls maximum length of generated response
- Balance between detail and API usage/cost

## Exercise Sections

The notebook includes multiple exercises marked with `# TODO`:

**Exercise 1**: Basic Prompts
- Experiment with different prompt styles
- Observe how outputs change

**Exercise 2**: Zero-Shot Learning
- Classify reviews, summarize text, translate languages
- Test model's generalization capabilities

**Exercise 3**: One-Shot Learning
- Write formal emails, simplify concepts, extract keywords
- Establish patterns with single examples

**Exercise 4**: Chain-of-Thought
- Decision-making processes
- Step-by-step explanations

**Exercise 5**: LCEL Chain with Custom Formatting
- Build a product review analyzer
- Create sentiment analysis pipelines

## Best Practices

✅ **DO:**
- Be specific and clear in instructions
- Provide relevant context
- Use examples for complex tasks
- Break down multi-step problems
- Iterate and refine prompts
- Test edge cases

❌ **DON'T:**
- Use vague or ambiguous language
- Provide contradictory instructions
- Assume model knowledge
- Skip examples for complex tasks
- Ignore parameter tuning
- Rely on single attempts

## Useful Patterns

### Classification Pattern
```python
prompt = """
Classify the following text into [categories].
Text: [your_text]
Category:
"""
```

### Summarization Pattern
```python
prompt = """
Summarize the following text in [number] sentences.
Text: [your_text]
Summary:
"""
```

### Question Answering Pattern
```python
prompt = """
Based on the following context:
[context]

Answer this question: [question]
Answer:
"""
```

### Chain-of-Thought Pattern
```python
prompt = """
[Problem description]

Think through this step-by-step:
"""
```

## Common Issues & Solutions

### Issue: Model returns incomplete or vague answers
**Solution**: 
- Increase `max_new_tokens`
- Provide more context in prompt
- Use few-shot examples
- Refine your instructions

### Issue: Responses are too creative/random
**Solution**:
- Decrease `temperature`
- Set `top_k` to 1
- Reduce `top_p`

### Issue: Model keeps repeating itself
**Solution**:
- Decrease `temperature`
- Use more specific instructions
- Add constraints in prompt

### Issue: API rate limits or timeouts
**Solution**:
- Add delays between requests
- Reduce `max_new_tokens`
- Check your API quota

## Further Resources

- [IBM Thinking - Prompt Engineering](https://www.ibm.com/think/topics/prompt-engineering)
- [OpenAI Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering)
- [Chain-of-Thought Prompting Paper](https://arxiv.org/abs/2201.11903)
- [Few-Shot Learning Paper](https://arxiv.org/abs/2005.14165)
- [LangChain Prompt Templates](https://python.langchain.com/docs/concepts/prompt_templates/)

## Next Steps

After completing this module:
1. Review your favorite prompting techniques
2. Create a personal prompt library
3. Practice with different domains (code, writing, analysis)
4. Move to the LangChain module for production applications

---

**Happy Prompting! 🧠**

Remember: Great prompts come from practice and iteration!
