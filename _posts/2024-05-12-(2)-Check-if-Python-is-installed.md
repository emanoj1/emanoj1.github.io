---
layout: post
site.posts
title: 2. Check if Python is installed
---

In my Bash Script (Python), I want to check if the Python program already has a .venv (virtual environment) present. 
If present, it returns a message, ".venv - virtual environment present". If not, it creates a new .venv file. 
Below is the script that uses Python's venv module to create the virtual environment.

```python
#!/bin/bash

if [ -d ".venv" ]; then
    echo ".venv - virtual environment present"
else
    python -m venv .venv
    echo ".venv - virtual environment created"
fi
```
This script checks if the .venv directory exists (-d ".venv"). 
If it does, it echoes the message stating that the virtual environment is present. 
If not, it creates a new virtual environment using Python's venv module (`python -m venv .venv`) and echoes a message confirming its creation.

Make sure to give execute permissions to this script using `chmod +x script_name.sh` so that it can be executed as a standalone script.

