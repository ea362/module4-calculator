# README.md — Modular Python Calculator (Module 4)
## Overview
This project is a modular, professional grade command line calculator application built for Module 4 of the course. It demonstrates advanced Python concepts including:
-	Object Oriented Programming (OOP)
-	Abstract base classes
-	Factory design patterns
-	Error handling using LBYL and EAFP
-	Modular architecture
-	Comprehensive unit testing with pytest
-	100% test coverage
-	Continuous Integration (CI) with GitHub Actions

The calculator runs in a REPL (Read Eval Print Loop) and supports addition, subtraction, multiplication, and division, along with helpful commands like help, history, and exit.
________________________________________
## Project Structure
```text
module4-calculator/
│
├── main.py
├── app/
│   ├── calculator/
│   │   └── __init__.py
│   ├── calculation/
│   │   └── __init__.py
│   └── operation/
│       └── __init__.py
│
└── tests/
    ├── test_calculator.py
    ├── test_calculations.py
    ├── test_operations.py
    └── conftest.py
```
### Module Responsibilities
- app/calculator — REPL interface, input parsing, history, commands
- app/calculation — Calculation classes + factory pattern
- app/operation — Arithmetic operations
- tests/ — Full pytest suite with parameterized tests and mocks
________________________________________
## Running the Application
### 1. Create and activate a virtual environment
python3 -m venv venv

source venv/bin/activate
### 2. Install dependencies
pip install pytest pytest-cov
### 3. Run the calculator
python main.py

You will see a REPL prompt where you can enter commands like:
- add 5 10
- subtract 20 3
- multiply 7 8
- divide 10 2
- history
- help
- exit
________________________________________
## Running Tests
### Run all tests
pytest
### Run tests with coverage
pytest --cov=app --cov-report=term-missing.

Your goal is 100% coverage, which this project achieves.
________________________________________
## Continuous Integration (GitHub Actions)
This project includes a CI workflow located at:

.github/workflows/python-app.yml

The workflow:
-	Installs dependencies
-	Runs all tests
-	Measures coverage
-	Fails the build if coverage is below 100%
  
This ensures code quality and prevents regressions.
________________________________________

## Key Features
### REPL Interface
- Continuous input loop
-	Clear prompts and feedback
-	Graceful handling of invalid input

### Modular Architecture
-	Clean separation of concerns
-	Extensible calculation system
-	Factory pattern for dynamic class creation

### Robust Error Handling
-	LBYL for input validation
-	EAFP for execution and parsing
-	Division by zero protection

### Comprehensive Testing
-	Unit tests for operations
-	Tests for calculation classes
-	Tests for factory behavior
-	Tests for REPL logic
-	Parameterized tests
-	Mocking of arithmetic operations
-	100% coverage
________________________________________

## Extending the Calculator
You can easily add new operations:
1.	Create a new Calculation subclass
2.	Implement the execute() method
3.	Register it with the factory:

        @CalculationFactory.register_calculation("power")
        
        class PowerCalculation(Calculation):
            def execute(self):
                  return self.a ** self.b
  	
The REPL will automatically support it.
