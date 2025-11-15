## GPU-Accelerated Data Science Agent

An intelligent agent built on **NVIDIA Nemotron Nano 9B v2** for natural language-to-code data analysis, accelerated entirely on the Kaggle GPU using `cudf.pandas`. The LLM runs locally via the `llama.cpp` HTTP server, providing a powerful, private, and efficient environment for data science tasks.

### Badges

![Model](https://img.shields.io/badge/Model-Nemotron%20Nano%209B%20v2-lightgrey)
![LLM Backend](https://img.shields.io/badge/LLM%20Backend-llama.cpp%20Server-lightgrey)
![GPU Acceleration](https://img.shields.io/badge/GPU%20Accel.-cuDF%20(pandas%20API)-lightgrey)
![Language](https://img.shields.io/badge/Language-Python-lightgrey)
![Platform](https://img.shields.io/badge/Platform-Kaggle%20Notebook-lightgrey)

---

### Key Features

* **Local LLM Execution:** Runs the **Nemotron Nano 9B v2** model locally for low-latency, private, and offline operation via the `llama-server` subprocess.
* **Full GPU Acceleration:** Uses **`cudf.pandas`** to automatically accelerate all data processing operations on the NVIDIA GPU.
* **Function Calling:** The Nemotron model is configured to use the `execute_python_code` tool, enabling it to generate, run, and self-correct Python code.
* **Persistent Context:** The environment maintains the DataFrame state (`df`) across conversation turns, enabling complex, multi-step analysis.

---

### Functionality & Uses

The agent is designed for high-speed, interactive data exploration by abstracting away the code barrier.

#### Core Functionality

* **Natural Language to Code:** Translates prompts into executable Python/pandas code.
* **GPU-Accelerated Execution:** Performs data manipulation and aggregation at high speed using cuDF.
* **Autonomous Error Correction:** Detects and fixes errors (e.g., `NameError`, logical flaws) in generated code automatically.
* **Persistent Memory:** Analyzes data iteratively without reloading or redefining variables.

#### Primary Use Cases

Exploratory Data Analysis (EDA), Statistical queries (e.g., calculating correlation), Data manipulation and cleaning, and Data visualization (charting).

---

### Example Interaction

The agent accepts natural language commands and translates them into GPU-accelerated code, returning the results directly.


#### Example Interaction Snippet

* **User Prompt:** Read the VGSales dataset and show the column names.
    * Agent Result: `['Rank', 'Name', 'Platform', 'Year', 'Genre', ...]`
* **User Prompt:** What are the top platforms from the year 2006?
    * Agent Result: `PS2, DS, PSP, X360, XB`

* **User Prompt:** Use line charts to show the difference between NA sales and EU sales. Make the colour of one green and the other blue
    * Agent Result:
      
      ![NA vs EU Sales Over Time Chart](sales.png)
