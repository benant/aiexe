# TODO

* 코드 실행 후 재생성시 코드 생성 이상하게 되는 오류 수정 필요.


# aiexe

Welcome to aiexe, the cutting-edge command-line interface (CLI) tool that integrates powerful AI capabilities directly into your terminal. Designed for developers, tech enthusiasts, and anyone interested in AI-powered automation, aiexe provides an easy-to-use yet robust platform for executing complex tasks with just a few commands. Harness the power of OpenAI's GPT models, Anthropic's Claude models, Ollama's versatile llama3 models, and Gemini models to boost your productivity and enhance your decision-making processes.

## Table of Contents
1. [Watch Our Demo](#watch-our-demo)
2. [Features](#features)
3. [Getting Started](#getting-started)
4. [Installation](#installation)
   - [Windows Installation](#windows-installation)
   - [macOS Installation](#macos-installation)
   - [Linux Installation](#linux-installation)
5. [Usage](#usage)
6. [Translation Feature](#translation-feature)
7. [Safety Features](#safety-features)
8. [Additional Python Environment Setup](#additional-python-environment-setup)
9. [Contribute](#contribute)
10. [Support](#support)
11. [Subscribe](#subscribe)

## Watch Our Demo
Watch our demo video on YouTube to get a quick overview of what aiexe can do for you! Click [here](https://www.youtube.com/watch?v=dvx-gFx6nUw) to watch the video.  
[![Video Label](http://img.youtube.com/vi/dvx-gFx6nUw/0.jpg)](https://youtu.be/dvx-gFx6nUw)  

## Features

- **Seamless Integration**: Easily integrate with OpenAI, Anthropic, Ollama, and Gemini AI models.
- **Flexible Commands**: Execute a variety of AI-driven tasks directly from your CLI.
- **Cross-Platform Compatibility**: Works on any system with Python support, including Linux, macOS, and Windows.

## Getting Started

### Prerequisites

Before you begin, ensure you have `npm` and Python installed on your system.

## Installation

### Windows Installation
1. Download and install Node.js from [nodejs.org](https://nodejs.org).
2. Download and install Python from [python.org](https://www.python.org/).
3. Run PowerShell as administrator and execute the following command to set the execution policy:
   ```powershell
   Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned -Force
   ```
   This command allows scripts signed by a trusted publisher to be run and avoids interruptions during the installation of `aiexe`. Be cautious with this setting, as it can potentially expose your system to security risks if scripts from untrusted sources are executed.
4. Install `aiexe` globally using npm:
   ```bash
   npm install aiexe -g
   ```
5. Start using `aiexe` by entering the command:
   ```bash
   aiexe
   ```

### macOS Installation
1. Download and install Node.js from [nodejs.org](https://nodejs.org).
2. Download and install Python from [python.org](https://www.python.org/).
3. Install `aiexe` globally using npm:
   ```bash
   sudo npm install aiexe -g
   ```
4. Start using `aiexe` by entering the command:
   ```bash
   aiexe
   ```

### Linux Installation
1. Download and install Node.js from [nodejs.org](https://nodejs.org).
2. Download and install Python from [python.org](https://www.python.org/).
3. Install `aiexe` globally using npm:
   ```bash
   sudo npm install aiexe -g
   ```
4. Start using `aiexe` by entering the command:
   ```bash
   aiexe
   ```

## Usage

`aiexe` can be used with various options. The basic usage is as follows:

```bash
aiexe [options] [prompt]
```

- `prompt`: Enter the prompt for the task to execute.

### Options

- `-V, --version`: Output the version number of `aiexe`.
- `-r, --resetconfig`: Reset the configuration and Python virtual environment to their initial state.
- `-s, --source <source>`: Specify the source language. The default is "auto".
- `-d, --destination <destination>`: Specify the destination language. The default is an empty string ("").
- `-c, --choosevendor`: Choose the LLM vendor.
- `-m, --choosemodel`: Choose the LLM model.
- `-p, --python <command>`: Run a command in the Python virtual environment.
- `-h, --help`: Display help information.

### Examples

1. Execute a task with a prompt:
   ```bash
   aiexe "Convert all jpg files in the /Users/kst/Downloads/data folder to black and white and place them in the /Users/kst/Downloads/data/grayscalephoto folder. If the folder does not exist, make it."
   ```

2. Choose the LLM vendor:
   ```bash
   aiexe -c
   ```

3. Choose the LLM model:
   ```bash
   aiexe -m
   ```

4. Run a command in the Python virtual environment:
   ```bash
   aiexe -p "pip install numpy pandas"
   ```
   Or
   ```bash
   aiexe -p "pip install -r requirements.txt"
   ```

## Translation Feature

`aiexe` provides a translation feature that allows you to translate prompts into different languages. To use the translation feature, specify the source language with the optional `-s` option and the destination language with the required `-d` option. The language specification uses ISO 639-1 language codes.

### ISO 639-1 Language Codes

ISO 639-1 is an international standard for representing languages with two-letter codes, established by the International Organization for Standardization (ISO).

For example:
- en: English
- fr: French
- ko: Korean
- ja: Japanese
- vi: Vietnamese
- es: Spanish
- de: German
- zh: Chinese
- ru: Russian
- it: Italian
- pt: Portuguese
- hi: Hindi

### Options

- `-s, --source <source>` (Optional): Specify the source language. The default is "auto", which automatically detects the source language. To specify a specific language, use its ISO 639-1 code.
- `-d, --destination <destination>` (Required): Specify the destination language using its ISO 639-1 code.

### Usage Examples

1. Translate from English to Korean:
   ```bash
   aiexe -s en -d ko "Run a command in the Python virtual environment"
   ```
   This command translates "Run a command in the Python virtual environment" to Korean.

2. Translate from Korean to English using automatic language detection:
   ```bash
   aiexe -d en "파이썬 가상 환경에서 명령어 실행하기"
   ```
   This command translates "파이썬 가상 환경에서 명령어 실행하기" to English. Since the `-s` option is not specified, it automatically detects the source language as Korean.

3. Translate using a pipeline:
   ```bash
   echo "Run a command in the Python virtual environment" | aiexe -s en -d ko
   ```
   This command passes "Run a command in the Python virtual environment" through a pipeline to `aiexe` and translates it to Korean.

The translation feature makes it more convenient to use `aiexe` in multilingual environments. Specify the appropriate source and destination languages or use a pipeline to translate prompts as needed.

## Safety Features

To ensure that generated code does not negatively impact your system or external environment, `aiexe` requires manual confirmation from the user before executing any commands. This feature enhances security by allowing you to evaluate and approve commands before they are run. Please be cautious and make sure you understand the purpose and implications of any AI-generated code before you use it.

**Disclaimer**: The user assumes full responsibility for the use of `aiexe`. Ensure that you operate in a safe environment and carefully consider the intent and consequences of the code you execute.

## Additional Python Environment Setup

When using `aiexe` to generate Python code, you might require additional Python packages to fully execute the generated scripts. To facilitate this, `aiexe` allows you to pre-install necessary Python packages into its virtual environment.

You can install individual packages using the command:
```bash
aiexe -p "pip install numpy pandas"
```

Alternatively, if you have a `requirements.txt` file that lists all of the necessary packages, you can install all of them at once with:
```bash
aiexe -p "pip install -r requirements.txt"
```

This feature ensures that all dependencies are resolved before executing any AI-generated Python code, providing a smoother and more efficient workflow.

## Contribute

Contributions are welcome! If you have improvements or bug fixes, feel free to fork the repository and submit a pull request.

## Support

If you need help or have any questions, please open an issue in the GitHub repository.

## Subscribe

Explore more exciting content about AI and coding on my YouTube channel [CodeTeller](https://www.youtube.com/@codeteller). Don't forget to subscribe for the latest updates and tutorials!

Harness the potential of `aiexe` and transform your terminal into a powerful AI command center!
