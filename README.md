# HELLO MCP – PYTHON MODEL CONTEXT PROTOCOL SERVER

**NAME:** SHAIK SHAMAN KHALID  
**REGISTRATION NUMBER:** 261FB04039

## 1. Project Overview

Hello MCP is a simple Python-based **Model Context Protocol (MCP) Server** designed to demonstrate how AI applications can interact with external tools through a standardized communication protocol.

The server provides three basic tools: greeting generation, arithmetic operations, and numerical data analysis. It uses the MCP Python SDK to expose these functionalities so that compatible MCP clients can discover and execute them.

This project introduces the fundamentals of MCP server development, tool registration, input handling, and structured responses.

## 2. Objectives

- Understand the fundamentals of Model Context Protocol (MCP).
- Develop a basic MCP server using Python.
- Register and expose custom tools.
- Perform arithmetic calculations.
- Analyze numerical datasets and generate statistical summaries.
- Connect the MCP server with compatible clients using standard input/output (stdio) transport.

## 3. Technologies Used

| Technology | Purpose |
|---|---|
| Python 3.10+ | Server development |
| MCP SDK | MCP server implementation |
| VS Code | Development environment |
| Virtual Environment | Dependency management |
| PowerShell | Running Python commands |
| JSON | Tool input and structured data exchange |

## 4. System Requirements

- Python version 3.10 or higher.
- Visual Studio Code or another Python IDE.
- MCP Python SDK (`mcp`).
- Windows operating system with PowerShell (commands can be adapted for other operating systems).

## 5. Project Setup

Open the project directory in VS Code and create a virtual environment.

```powershell
py -m venv .venv
```

Activate the virtual environment:

```powershell
.\.venv\Scripts\Activate.ps1
```

Install the MCP Python SDK:

```powershell
python -m pip install mcp
```

If virtual environment activation is restricted, install the package directly:

```powershell
.\.venv\Scripts\python.exe -m pip install mcp
```

## 6. Project Structure

```text
hello-mcp/
│
├── server.py
│
├── .vscode/
│   └── mcp.json
│
├── .venv/
│
└── README.md
```

**File descriptions:**

- `server.py`: Contains the MCP server implementation and registered tools.
- `.vscode/mcp.json`: Configures the MCP server for integration with VS Code.
- `.venv/`: Stores the project's isolated Python environment.
- `README.md`: Contains project documentation and execution instructions.

## 7. MCP Tools and Functionalities

The server exposes the following three tools:

### A. get_greeting

**Purpose:** Generates a personalized greeting message for the supplied name.

- Input: `name` (String)
- Output: Greeting message.

Example input:

```json
{
  "name": "Students"
}
```

Expected output:

```text
Hello, Students! Your first MCP tool works.
```

### B. add_numbers

**Purpose:** Performs addition of two integer values and returns their sum.

- Input: `a` (Integer), `b` (Integer)
- Output: Sum of the two numbers.

Example input:

```json
{
  "a": 10,
  "b": 20
}
```

Expected output:

```text
30
```

### C. analyze_data

**Purpose:** Analyzes a list of numerical values and generates basic statistical information.

- Input: `numbers` (List of Numbers)
- Output: Statistical summary.

The tool calculates:

1. **Count:** Total number of elements.
2. **Minimum:** Smallest value in the dataset.
3. **Maximum:** Largest value in the dataset.
4. **Average:** Arithmetic mean, rounded to two decimal places.
5. **Status:** Indicates whether the analysis was successful.

Example input:

```json
{
  "numbers": [2, 4, 6]
}
```

Expected output:

```json
{
  "status": "success",
  "count": 3,
  "min": 2,
  "max": 6,
  "average": 4.0
}
```

**Empty dataset handling:**

If an empty list is provided, the tool returns an error status with an appropriate message instead of attempting to calculate statistics.

## 8. Execution Procedure

Run the MCP server using the following command from the project directory:

```powershell
.\.venv\Scripts\python.exe server.py
```

The server communicates through the **stdio transport**, which uses standard input and output for communication between the MCP host and the server.

When integrated with VS Code, the `.vscode/mcp.json` configuration allows the compatible MCP host to launch the server automatically.

## 9. Expected Results

After successful setup and execution:

- The MCP server starts without dependency errors.
- The greeting tool returns a personalized message.
- The addition tool calculates the sum correctly.
- The data analysis tool returns count, minimum, maximum, and average.
- Empty input is handled gracefully.
- Compatible MCP clients can discover and invoke the registered tools.

## 10. Advantages

- Simple and easy-to-understand implementation.
- Demonstrates practical MCP server development.
- Supports multiple independent tools.
- Provides structured numerical analysis.
- Uses an isolated Python environment for dependency management.
- Can be integrated with compatible MCP clients.

## 11. Conclusion

The Hello MCP project demonstrates the development and execution of a basic Model Context Protocol server using Python. By implementing greeting, arithmetic, and numerical analysis tools, the project provides practical knowledge of MCP architecture, tool registration, input processing, and client-server communication.

It establishes a foundation for developing advanced MCP applications that integrate AI assistants with external tools, databases, APIs, and other services.
