# InlineGPT

InlineGPT is a Python package that integrates Google's Generative AI models directly into your Python applications to provide inline error handling and suggestions for code corrections.

## Installation

You can install InlineGPT via pip:

```bash
pip install InlineGPT
```

## Getting Started

To use InlineGPT, you need to obtain an API key from [Google AI Studio](https://aistudio.google.com/app/apikey).

### Example Usage

```python
from inline.inlinegpt import InlineGPT
import os

# Initialize your API KEY
gpt = InlineGPT(os.environ.get('G_API_KEY')) 

try:
    result = 10 / 0
except ZeroDivisionError as e:
    print(f"Error: {e}")
    gpt.get_solution("test.py", e)

```

### Output

The `get_solution` method analyzes the code in `file_name` and the provided `error_message`, then generates a response suggesting how to resolve the error using Google's Generative AI models.

## Contributing

We welcome contributions to InlineGPT! Please fork the repository and submit pull requests to contribute.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Issues

If you encounter any issues with InlineGPT or have suggestions for improvements, please open an issue on [GitHub](https://github.com/yourusername/InlineGPT/issues).

---

### Additional Notes:

- **Dependencies**: InlineGPT relies on `google.generativeai` for its AI capabilities. Ensure you have the necessary permissions and API key from Google AI Studio.
- **Error Handling**: If the API key is invalid or not provided, InlineGPT will raise an initialization error.