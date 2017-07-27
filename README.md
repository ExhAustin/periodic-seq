# Periodic Sequence Loop Counter
- Author: Austin Wang
- Year: 2017
- Requirements: Numpy (Matplotlib for visulization) (See requirements.txt for full details)

## Introduction
- Counts cycle occurences in periodic sequence regardless of noise
- Application: Counting loops in execution of flow chart with information from log files

## File list
**PeriodCounter.py**
Primary module for counting periodic occurences, with countains two classes
- OnlinePeriodCounter: Main functionality of the counter
  - __init__(window, margin): initializer, counts diagonally if margin < 0
  - addElement(e): member function, parses new element from the sequence and updates count
  - count: member variable, current estimate of number of loops in sequence
- PeriodCounter: Counts entire sequence
  - __init__(window, margin): initializer, counts diagonally if margin < 0
  - count(seq): member function, calls OnlinePeriodCounter to count number of loops in seq

**count.py**  
Example program of counting TM5 log files  
Usage: `$python count.py <parsed_log_file_path>`  

**preprocess.py**  
Preprocesses a TM5 log file, leaving only names of executed nodes and errors  
Usage: `$python preprocess.py <log_file_path> <output_file_path>`  

**visualize.py**  
Visualizes the shift chart of first n elements of a sequence file  
Requires matplotlib  
Usage: `$python visualize.py <log_file_path>`  

**datasets/**  
Contains sequence data  

**random_noise/**  
Contains code related to creating and analyzing random sequences  
Used in the development process  

**requirements.txt**  
Python library list (output file of pip freeze)  