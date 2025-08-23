# LLM Quantum Computing Assignment

## Overview

This assignment demonstrates the integration of Large Language Models (LLMs) with the OpenRouter API to generate educational content about quantum computing. The project showcases how to interact with different AI models through a unified API interface and generate markdown responses for educational purposes.

## Project Description

The project consists of a Python script that:
- Connects to the OpenRouter API to access various LLM models
- Sends prompts about quantum computing concepts
- Generates educational responses suitable for different age groups
- Saves the AI-generated responses in markdown format
- Demonstrates the capabilities of different AI models (DeepSeek and Gemma)

## Features

- **API Integration**: Seamless integration with OpenRouter API for accessing multiple LLM models
- **Environment Configuration**: Secure API key management using `.env` files
- **Error Handling**: Comprehensive error handling for API requests and file operations
- **Markdown Output**: Automatic generation of formatted markdown files
- **Model Flexibility**: Easy switching between different AI models
- **Educational Content**: Focus on explaining complex topics like quantum computing

## Prerequisites

- Python 3.7 or higher
- OpenRouter API key (free tier available)
- Basic understanding of Python programming

## Installation

1. **Clone or download the project files**
2. **Install required dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up environment variables**:
   Create a `.env` file in the project root with your OpenRouter API key:
   ```
   OPENROUTER_API_KEY=your_api_key_here
   ```

## Configuration

### Getting an OpenRouter API Key

1. Visit [OpenRouter](https://openrouter.ai/)
2. Sign up for a free account
3. Generate an API key from your dashboard
4. Add the key to your `.env` file

### Available Models

The script is configured to work with various models available through OpenRouter:
- `deepseek/deepseek-r1-0528:free` - DeepSeek's latest model
- `google/gemma-3n-e2b-it:free` - Google's Gemma model
- Many other models available through the OpenRouter platform

## Usage

### Basic Usage

1. **Run the main script**:
   ```bash
   python llm_Quantum.py
   ```

2. **The script will**:
   - Send a prompt about quantum computing to the configured AI model
   - Generate a response
   - Save the result to `ai_response.md`

### Customizing the Script

#### Changing the Prompt

Modify the `prompt` variable in the `main()` function:
```python
prompt = "Your custom prompt here"
```

#### Switching Models

Change the model parameter in the `getLLM_Result()` call:
```python
# For DeepSeek model
result = getLLM_Result(prompt, "deepseek/deepseek-r1-0528:free")

# For Gemma model
result = getLLM_Result(prompt, "google/gemma-3n-e2b-it:free")
```

#### Custom Output Filename

Modify the `output_file` variable:
```python
output_file = "your_custom_filename.md"
```

### Using the Function Directly

You can also use the `getLLM_Result()` function in other scripts:

```python
from llm_Quantum import getLLM_Result

response = getLLM_Result("Explain machine learning", "deepseek/deepseek-r1-0528:free")
print(response)
```

## Project Structure

```
Assignment 1/
├── llm_Quantum.py          # Main Python script
├── requirements.txt         # Python dependencies
├── .env                    # Environment variables (create this)
├── .gitignore             # Git ignore file
├── Readme.md              # This documentation file
├── deepseek_ai_response.md # Sample response from DeepSeek model
└── gemma_ai_response.md    # Sample response from Gemma model
```

## API Response Format

The script generates markdown files with the following structure:
```markdown
# AI Model Response

## Prompt
[Your input prompt]

## Response
[AI-generated response]

---
*Generated using OpenRouter API*
```

## Error Handling

The script includes comprehensive error handling for:
- Missing API keys
- Network request failures
- JSON parsing errors
- File writing errors
- General exceptions

## Sample Outputs

The project includes two sample responses:
1. **DeepSeek Response**: A detailed explanation of quantum computing with analogies and examples
2. **Gemma Response**: A comprehensive overview with practical applications and limitations

Both responses demonstrate how different AI models can approach the same educational topic with varying styles and depth.

## Limitations and Considerations

- **API Rate Limits**: Free tier may have usage limitations
- **Model Availability**: Some models may not be available at all times
- **Response Quality**: AI responses may vary in accuracy and completeness
- **Cost**: While free tier is available, extensive usage may incur costs

## Troubleshooting

### Common Issues

1. **"Please set OPENROUTER_API_KEY in your .env file"**
   - Ensure your `.env` file exists and contains the correct API key
   - Check that the `.env` file is in the same directory as the script

2. **API request errors**
   - Verify your API key is valid
   - Check your internet connection
   - Ensure the model name is correct

3. **File writing errors**
   - Check write permissions in the current directory
   - Ensure sufficient disk space

### Getting Help

- Check the OpenRouter documentation for API-related issues
- Verify your Python environment and dependencies
- Review the error messages for specific guidance

## Future Enhancements

Potential improvements for the project:
- Web interface for easier interaction
- Support for multiple prompts and batch processing
- Response comparison between different models
- Integration with other AI APIs
- Enhanced markdown formatting options
- Response caching and storage

## Contributing

This is an educational assignment, but suggestions for improvements are welcome:
- Code optimization
- Additional features
- Better error handling
- Documentation improvements

## License

This project is created for educational purposes as part of an AI training assignment.

## Acknowledgments

- OpenRouter for providing access to multiple LLM models
- DeepSeek and Google for their AI models
- Python community for the excellent libraries used in this project

---
