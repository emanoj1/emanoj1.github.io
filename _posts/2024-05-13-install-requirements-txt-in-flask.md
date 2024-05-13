---
layout: post
date: 2024-05-13 19:25:00 +1000
title: 8. Install requirements.txt in a Flask module
tag: Flask
---

To install the dependencies listed in a `requirements.txt` file for a Flask project, you can use the `pip` tool, which is the package installer for Python. Follow these steps:

1. **Navigate to the Project Directory:**
   Open a terminal or command prompt and navigate to the directory where your Flask project is located. Use the `cd` command to change the current directory.

   ```bash
   cd path/to/your/flask/project
   ```

2. **Activate Virtual Environment (Optional but recommended):**
   If you are using a virtual environment (which is recommended for managing dependencies in Python projects), activate it. If you don't have a virtual environment, you can skip this step.

   ```bash
   # On Windows
   venv\Scripts\activate

   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install Dependencies:**
   Run the following command to install the dependencies listed in the `requirements.txt` file:

   ```bash
   pip install -r requirements.txt
   ```

   This command reads the dependencies from `requirements.txt` and installs them.

4. **Verify Installation:**
   After the installation is complete, you can verify that the packages were installed by checking the active environment:

   ```bash
   pip list
   ```

   This will display a list of installed packages along with their versions.

That's it! You've successfully installed the dependencies for your Flask project based on the specifications in the `requirements.txt` file. 
It's good practice to include the `requirements.txt` file in your version control system (e.g., Git) so that others can easily replicate the environment.

---

If you are interested in studying Flask, I highly recommend this book: 
### The Flask Mega-Tutorial
by Miguel Grinberg
[Available on Amazon](https://amzn.to/3WyUd8D)!
