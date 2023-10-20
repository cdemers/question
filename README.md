# Question App

## Description

The Question App is a command-line interface (CLI) tool that allows you to interact with OpenAI's GPT-4 model. Pose a question or query, and get a detailed response right in your terminal. The app is designed for quick, efficient, and insightful answers.

## Features

- Query GPT-4 directly from your terminal
- Supports Markdown formatting for terminal output
- Efficient error handling and logging
- Quick and easy installation

## Requirements

- Python 3.x
- OpenAI API key

## Installation

### macOS (via Homebrew)

You can install the Question App using Homebrew:

Option 1: Direct install
```bash
brew install cdemers/tools/question
```

Option 2: Tap first, then install
```bash
brew tap cdemers/tools
brew install question
```

### Other Platforms

Clone the repository and run the Python script directly.

```bash
git clone https://github.com/cdemers/question.git
cd question
./question.py "Your query here"
```

## Usage

To use the app, simply run the following command:

```bash
question "What is the meaning of life?"
```

For version information:

```bash
question --version
```

## Environment Variables

- `OPENAI_API_KEY`: Your OpenAI API key
- `LOG_LEVEL`: Logging level (default is `WARNING`)

## Contributing

Feel free to open issues or PRs if you have suggestions or bug reports.

