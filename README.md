# Ollama API Interaction Script

![alt text](images/llava.gif)

## Introduction

This script facilitates interaction with the Ollama API, enabling efficient communication with models that support single message responses, chat sessions, and multimodal inputs (including images). It's designed to work with the Ollama API, allowing users to easily integrate Large Language Model (LLM) interactions into their applications.

## Features

- **Single Message and Chat Capabilities**: Send a single message or initiate a chat session with the model.
- **Multimodal Support**: Supports sending images along with text prompts to multimodal models.
- **Streaming Responses**: Option to stream responses for real-time interaction.
- **Error Handling**: Robust error handling and informative messages for troubleshooting.
- **Environment Integration**: Automatically fetches API URL from environment variables for ease of configuration.

## Prerequisites

To use this script, you will need:

- Python 3.6 or higher.
- `requests` library installed. Install it via pip if you haven't already:
  ```bash
  pip install requests
  ```
- Access to the Ollama API and a valid API key if required.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/ronigold/Ollama.git
   ```
2. Navigate to the cloned directory:
   ```bash
   cd Ollama
   ```
3. Ensure you have Python and the required packages installed.

## Usage

### Setting API URL

Set the `API_URL` environment variable to point to your Ollama API endpoint. You can set it temporarily in the terminal:
```bash
export API_URL='http://localhost:11434/api'
```
Or permanently by adding it to your `.bashrc` or `.zshrc`.

### Running the Script

To interact with the API, run the `interact_with_ollama` function from your Python environment:

- **For Sending Text Prompts**:
  ```python
  interact_with_ollama(
      model = 'llama3',
      prompt='Why is the sky blue?'
  )
  ```

- **For a Chat Session**:
  ```python
  interact_with_ollama(
      model = 'openhermes2.5-mistral',
      messages=messages = [
        {'role': 'user', 'content': 'What is machine learning?'},
        {'role': 'assistant', 'content': 'Machine learning is a field of AI that enables systems to learn and improve from experience without being explicitly programmed.'
        {'role': 'user', 'content': 'interesting! How do these systems learn without explicitly programmed?'},}
        ]
    )
  ```

- **For Multimodal Interaction**:
  ```python
  interact_with_ollama(
      model = 'llava',
      prompt='What is strange about this image?', 
      image_path='path/to/image.jpg'
  )
  ```

### Output Handler

You can customize how the outputs are handled by providing a custom function to `output_handler`. By default, it prints messages to the console.

## Documentation

Refer to the inline comments in the script for detailed documentation on each function and parameter.

## Blog Reference

For more information on setting up and using the Ollama API, refer to the blog post: [Running Llama 3 on Personal Linux Hardware (GPU/CPU)](https://example.com/running-llama3).

## Contribution

Contributions to the script are welcome! Please fork the repository and submit a pull request with your enhancements.

## License

Distributed under the MIT License. See `LICENSE` for more information.
