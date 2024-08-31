# Bash Scripting Cheatsheet

![Bash](https://img.shields.io/badge/Bash-v5.1+-blue.svg) ![License](https://img.shields.io/github/license/vfedotovs/bash-scripting-cheatsheet)

## Overview

Welcome to the **Bash Scripting Cheatsheet** repository! This project aims to provide a comprehensive collection of Bash scripting examples, commands, and best practices. Whether you're a beginner or an experienced developer, this cheatsheet is designed to help you quickly find solutions to common Bash scripting tasks and improve your scripting skills.

## Table of Contents

- [Introduction](#introduction)
- [Getting Started](#getting-started)
- [Cheatsheet Contents](#cheatsheet-contents)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Bash is a powerful scripting language used for automating tasks, managing systems, and creating utilities. This cheatsheet serves as a quick reference guide for common Bash commands, patterns, and practices that are useful in day-to-day scripting.

## Getting Started

### Prerequisites

Before using this cheatsheet, make sure you have Bash installed on your system. Most Unix-like operating systems, including Linux and macOS, come with Bash pre-installed. You can check your Bash version by running:

```bash
bash --version
```

## Cloning the Repository
To use the cheatsheet locally, clone the repository to your machine:

```bash
git clone https://github.com/vfedotovs/bash-scripting-cheatsheet.git
cd bash-scripting-cheatsheet
```

## Cheatsheet Contents
This repository is organized into various sections, each covering different aspects of Bash scripting:

Basic Commands: Commonly used Bash commands and utilities.   
Control Structures: Loops, conditionals, and case statements.   
Functions: Defining and using functions in Bash.   
[Arrays](arrays.md): Working with indexed and associative arrays.   
[String Manipulation](strings.md): Techniques for handling and processing strings.   
File Operations: Reading, writing, and manipulating files.   
Process Management: Running, managing, and automating processes.   
Debugging: Tips and commands for debugging Bash scripts.   
Best Practices: Guidelines for writing clean, maintainable scripts.   

## Examples
Here are some examples of the scripts and commands you'll find in this cheatsheet:

1. Looping Over an Array
```bash
declare -a fruits=("Apple" "Banana" "Cherry")

for fruit in "${fruits[@]}"; do
  echo "I like $fruit"
done
```

2. Checking if a File Exists
```bash
if [ -f "/path/to/file" ]; then
  echo "File exists."
else
  echo "File does not exist."
fi
```

3. Using a Function to Sum Numbers
```bash
sum_numbers() {
  local sum=0
  for number in "$@"; do
    sum=$((sum + number))
  done
  echo "Sum: $sum"
}

sum_numbers 1 2 3 4 5
```

## Contributing
Contributions are welcome! If you'd like to add new examples, fix issues, or improve the content, please feel free to submit a pull request. Before contributing, please review the contributing guidelines.

## License
This repository is licensed under the MIT License. See the LICENSE file for more information.
