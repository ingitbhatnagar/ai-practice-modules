# AI Practice Modules

A comprehensive repository for practicing and understanding key AI concepts through interactive Jupyter notebooks. Each module contains a complete, self-contained notebook covering a specific AI topic.

## Repository Structure

```
ai-practice-modules/
├── README.md
├── requirements.txt
├── .env.example
└── modules/
    ├── prompt_engineering/
    │   ├── README.md
    │   └── In-Context Learning and Prompt Templates for Advanced AI.ipynb
    ├── langchain/
    │   ├── README.md
    │   └── (notebook to be added)
    └── mcp/
        ├── README.md
        └── (notebook to be added)
```

## Modules

### 1. Prompt Engineering
Master the fundamentals and advanced techniques of prompt engineering:
- Basic prompts
- Zero-shot prompting
- One-shot prompting
- Few-shot prompting
- Chain-of-thought (CoT) reasoning
- Self-consistency techniques
- Practical applications with LangChain

**Notebook**: `modules/prompt_engineering/In-Context Learning and Prompt Templates for Advanced AI.ipynb`

### 2. LangChain
(Coming soon) - Building applications with LangChain framework

### 3. MCP (Model Context Protocol)
(Coming soon) - Working with Model Context Protocol

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/ingitbhatnagar/ai-practice-modules.git
cd ai-practice-modules
```

### 2. Set Up Environment

#### Option A: Using Python venv (Recommended)
```bash
# Create virtual environment
python3 -m venv venv

# Activate virtual environment
# On macOS/Linux:
source venv/bin/activate
# On Windows:
venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

#### Option B: Using Conda
```bash
conda create -n ai-practice python=3.10
conda activate ai-practice
pip install -r requirements.txt
```

### 3. Configure Your LLM Provider

Copy the environment template and add your credentials:
```bash
cp .env.example .env
```

Edit `.env` with your LLM provider details (see instructions below).

### 4. Start Jupyter
```bash
jupyter notebook
```

Navigate to the module you want to explore and open the notebook.

## LLM Configuration

Each notebook supports multiple LLM providers. Configure your preferences in the notebook:

### IBM Watsonx.ai
```python
from langchain_ibm import WatsonxLLM

llm = WatsonxLLM(
    model_id="ibm/granite-4-h-small",  # or your preferred model
    url="https://us-south.ml.cloud.ibm.com",
    project_id="your-project-id",
    params={...}
)
```

### OpenAI
```python
from langchain_openai import ChatOpenAI

llm = ChatOpenAI(
    model="gpt-4",
    api_key="your-api-key"
)
```

### Anthropic Claude
```python
from langchain_anthropic import Anthropic

llm = Anthropic(
    model="claude-3-opus",
    api_key="your-api-key"
)
```

### Generic/Other Providers
```python
# Modify the llm_model() function in your notebook
# to use your preferred LLM provider
```

## Prerequisites

- Python 3.8+
- Jupyter Notebook or JupyterLab
- API keys for your chosen LLM provider
- Basic understanding of Python and prompt engineering concepts

## How to Use These Notebooks

1. **Read the Overview**: Each notebook starts with context and learning objectives
2. **Follow Examples**: Study the provided examples for each concept
3. **Complete Exercises**: Work through marked exercises (look for `# TODO` comments)
4. **Experiment**: Modify prompts, parameters, and try different approaches
5. **Document Learnings**: Add notes about what works and what doesn't

## Key Features

✅ **Self-Contained**: Each notebook is complete and can be used independently  
✅ **Generic LLM Integration**: Easy to swap LLM providers  
✅ **Practical Examples**: Real-world use cases and patterns  
✅ **Progressive Learning**: Build from basics to advanced techniques  
✅ **Interactive**: Jupyter environment for immediate experimentation  
✅ **Well-Documented**: Clear explanations and comments throughout  

## Tips for Success

1. **Start Sequential**: Follow the module order for best learning outcomes
2. **Run and Modify**: Don't just read—execute and experiment with code
3. **Take Notes**: Document patterns that work for your use cases
4. **Save Your Work**: Keep copies of successful prompts and configurations
5. **Share Findings**: Contribute improvements back to the repository

## Environment Variables

Use `.env` file for sensitive information:

```env
# IBM Watsonx.ai
WATSONX_URL=https://us-south.ml.cloud.ibm.com
WATSONX_PROJECT_ID=your-project-id
WATSONX_API_KEY=your-api-key

# OpenAI
OPENAI_API_KEY=your-api-key

# Anthropic
ANTHROPIC_API_KEY=your-api-key
```

**Important**: Never commit `.env` files with real credentials!

## Troubleshooting

### Kernel Issues
If you encounter kernel problems:
```bash
jupyter notebook --ip=127.0.0.1 --port=8888 --no-browser
```

### Dependency Issues
```bash
pip install --upgrade -r requirements.txt
```

### LLM Connection Issues
- Verify your API keys are correct
- Check your internet connection
- Ensure your LLM provider account is active and has available quota

## References

- [IBM Prompt Engineering Guide](https://www.ibm.com/think/topics/prompt-engineering)
- [OpenAI Prompt Engineering Best Practices](https://platform.openai.com/docs/guides/prompt-engineering)
- [LangChain Documentation](https://python.langchain.com/)
- [Chain-of-Thought Prompting](https://arxiv.org/abs/2201.11903)
- [Few-Shot Learning with LLMs](https://arxiv.org/abs/2005.14165)

## Contributing

Contributions are welcome! To add a new module:

1. Create a new directory under `modules/`
2. Add a `README.md` with module overview
3. Add your Jupyter notebook with the naming convention: `YourTopicName.ipynb`
4. Ensure generic LLM integration (placeholders for API keys)
5. Include examples and exercises
6. Submit a pull request

## License

MIT License - Feel free to use this for learning purposes

---

**Happy Learning! 🚀**

Start with the Prompt Engineering module to learn how to effectively communicate with LLMs!
