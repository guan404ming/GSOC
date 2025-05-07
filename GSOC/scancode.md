# GSoC 2025 Proposal: Enhancing ScanCode Toolkit with Variable License Section Support

## Basic Information

- **Name:** Guan-Ming (Wesley) Chiu
- **GitHub:** [https://github.com/guan404ming](https://github.com/guan404ming)
- **Email:** <guanmingchiu@gmail.com>
- **Location:** Taipei, Taiwan (GMT+8)

## About Me

Hi, I'm Guan-Ming Chiu! I'm an Information Management student at National Taiwan University (NTU), and I'm also a member of the NumPy organization. Currently, I'm gaining practical experience as a Frontend Developer intern at Microsoft. I enjoy working with a variety of technologies, including Python, JavaScript/TypeScript, and web frameworks. I'm interested in the complexities of software licensing and believe that improving tools like ScanCode Toolkit is crucial for ensuring compliance and fostering a healthy open-source ecosystem. I'm eager to apply my analytical and coding skills to contribute to this project.

## Why ScanCode?

I'm particularly drawn to this project because it directly addresses a critical challenge in software compliance. Improving ScanCode Toolkit's ability to accurately detect licenses with variable sections will have a significant impact on open-source projects and organizations that rely on accurate license information. I'm eager to learn more about the intricacies of license detection and contribute to a tool that plays a vital role in ensuring software transparency. This project aligns with my interest in legal aspects of open source and will allow me to apply my Python skills in a meaningful way. I'm committed to delivering high-quality, well-documented code and working closely with the mentors to achieve the project goals.

## Project Description

This project aims to enhance the ScanCode Toolkit's license detection capabilities by implementing support for variable license sections, aligning with SPDX matching guidelines. Current license detection often struggles with variations in license texts, such as differing copyright holders, years, or other non-essential phrases. This proposal addresses this issue by:

1. **Supporting Grammar for Variability in License Rules:** Implementing a mechanism to define flexible license rules that can accommodate variations (e.g., using brackets to denote optional text, specifying a range of words).
    - **Detailed Explanation:** Develop a syntax or grammar within ScanCode Toolkit that allows license rules to include placeholders or patterns for variable elements, ensuring compliance with SPDX matching guidelines regarding optional and variable text handling.
    - **Example:** Instead of a strict rule like "Copyright (c) 2023," the system could handle "Copyright (c) [Year]," where "[Year]" can match any year, aligning with the SPDX approach to handling variable text.
2. **Analyzing License Rules and Identifying Variable Sections:** Conducting a comprehensive analysis of existing license rules to identify common variable patterns and potential areas for improvement, focusing on patterns recognized by SPDX matching. This analysis will aim to reduce redundancy and create more robust rules.
    - **Detailed Explanation:** Systematically review the existing license rules within ScanCode Toolkit, categorizing variations found (e.g., copyright years, holder names, optional clauses), and identifying patterns that can be generalized into flexible rules, while considering SPDX handling of comments and text normalization.
    - **Example:** Create a spreadsheet or database to track each license rule, noting variable sections and common patterns, referencing SPDX guidelines for text processing and comparison.
3. **Enhancing License Detection Post-processing:** Improving the post-processing stage of license detection to handle cases where license texts contain extra words or minor deviations from the defined rules, ensuring alignment with SPDX's text comparison methodologies.
    - **Detailed Explanation:** Modify the post-processing stage to handle minor discrepancies between detected license text and defined rules, including handling extra words, slight misspellings, or punctuation variations, leveraging SPDX's approach to text normalization and difference detection.
    - **Example:** Implement fuzzy matching or edit distance algorithms, considering SPDX's text comparison logic, to identify licenses even with small deviations.
4. **Developing Scripts for Rule Updates:** Creating scripts to automate the process of adding variable sections to license rules based on analysis of detection issues (e.g., common variations observed in BSD license detections), while ensuring compatibility with SPDX license matching principles.
    - **Detailed Explanation:** Create Python scripts that automatically add or modify variable sections in license rules, using analysis from step 2 to identify common variations and apply the new grammar/syntax, ensuring consistency with SPDX's handling of license text and templates.
    - **Example:** A script that scans failed license detections, identifies common year variations in BSD licenses, and updates corresponding rules, adhering to SPDX's license matching guidelines.

## Goals

1. **Implement a grammar or rule syntax to represent variability in license rules, aligning with SPDX matching guidelines.**
    - Develop a clear and well-documented syntax for defining variable sections within license rules, consistent with SPDX's text handling and comparison.
2. **Analyze existing ScanCode Toolkit license rules to identify and categorize variable sections, considering SPDX patterns.**
    - Produce a comprehensive report detailing the analysis of existing license rules and identified variable patterns, referencing SPDX guidelines for text processing.
3. **Modify the ScanCode Toolkit's license detection logic to utilize the new variability grammar, ensuring SPDX compatibility.**
    - Integrate the new grammar into the license detection logic to handle variable rules, aligning with SPDX's approach to license text comparison.
4. **Enhance post-processing to handle minor variations and extra words in license texts, following SPDX methodologies.**
    - Improve the post-processing stage to handle discrepancies and minor deviations, leveraging SPDX's text normalization and difference detection techniques.
5. **Develop Python scripts to automate the addition of variability to license rules, consistent with SPDX principles.**
    - Create scripts to automate the process of updating license rules based on analysis, adhering to SPDX's license matching guidelines.
6. **Improve the accuracy and robustness of ScanCode Toolkit's license detection, ensuring alignment with SPDX.**
    - Enhance overall accuracy and reliability of license detection, consistent with SPDX's text comparison and matching criteria.
7. **Provide comprehensive documentation for the new features and scripts, referencing SPDX guidelines.**
    - Document new features and scripts for developers and users, referencing relevant SPDX guidelines for license matching.

## Deliverables

1. Enhanced license rule grammar implemented in ScanCode Toolkit, aligned with SPDX matching.
2. Analysis report on existing license rules and identified variable sections, considering SPDX patterns.
3. Modified ScanCode Toolkit license detection logic with support for variable rules, ensuring SPDX compatibility.
4. Improved license detection post-processing functionality, following SPDX methodologies.
5. Python scripts for automating license rule updates, consistent with SPDX principles.
6. Unit tests and integration tests for new features, ensuring alignment with SPDX.
7. Documentation for developers and users, referencing SPDX guidelines for enhanced license detection.

## Project Plan and Timeline

### Phase 1: Research and Design (Weeks 1-3)

- **Week 1 (5/8-6/1): Research and Setup**
  - Set up the development environment.
  - Familiarize with the ScanCode Toolkit codebase, especially the license detection module.
  - Review existing license rules and SPDX matching guidelines.
  - Research and propose a grammar/syntax for representing variability, aligning with SPDX.
- **Week 2 (6/2-6/8): Design and Rule Analysis**
  - Finalize the grammar/syntax design with mentors, considering SPDX principles.
  - Begin analyzing existing license rules to identify variable patterns, referencing SPDX guidelines.
- **Week 3 (6/9-6/15): Rule Analysis and Logic Design**
  - Complete the analysis of license rules and document findings, considering SPDX patterns.
  - Start designing modifications to the license detection logic, ensuring SPDX compatibility.

### Phase 2: Implementation (Weeks 4-9)

- **Weeks 4-6 (6/16-7/6): Grammar & Logic Implementation and Unit Tests**
  - Implement the new grammar/syntax in ScanCode Toolkit, aligned with SPDX.
  - Modify the license detection logic to handle variable rules, ensuring SPDX compatibility.
  - Write unit tests for core functionality, ensuring alignment with SPDX.
- **Weeks 7-9 (7/7-7/27): Post-processing, Automation Scripts, and Unit Tests**
  - Implement enhanced post-processing for handling variations, following SPDX methodologies.
  - Develop Python scripts for automating rule updates, consistent with SPDX principles.
  - Write unit tests for post-processing and scripting, ensuring alignment with SPDX.

### Phase 3: Testing and Documentation (Weeks 10-12)

- **Weeks 10-11 (7/28-8/10): Extensive and Integration Testing**
  - Perform extensive testing with a large dataset, ensuring SPDX alignment.
  - Address bugs and issues, considering SPDX principles.
  - Write integration tests, ensuring alignment with SPDX.
- **Week 12 (8/11-8/17): Documentation and Finalization**
  - Write comprehensive documentation, referencing SPDX guidelines.
  - Finalize code and prepare for submission.

## Example Code Snippets

### 1. Implementing a simple grammar for variable years in copyright statements

```python
import re

def match_copyright_year(text):
    """Matches copyright statements with variable years."""
    pattern = r"Copyright \(c\) (\d{4}|\\[Year\\])"
    match = re.search(pattern, text)
    if match:
        year = match.group(1)
        if year == "[Year]":
            return "Year is variable"
        else:
            return f"Copyright year: {year}"
    return None

# Example usage
print(match_copyright_year("Copyright (c) 2023"))
print(match_copyright_year("Copyright (c) [Year]"))
print(match_copyright_year("This is some text"))
```

### 2. Script to automatically add variable sections to license rules

```python
import json

def update_license_rules(rules_file, variable_patterns):
    """Updates license rules with variable sections."""
    with open(rules_file, 'r') as f:
        rules = json.load(f)

    for rule in rules:
        for pattern in variable_patterns:
            if pattern['original'] in rule['text']:
                rule['text'] = rule['text'].replace(pattern['original'], pattern['variable'])

    with open(rules_file, 'w') as f:
        json.dump(rules, f, indent=4)

# Example usage
rules_file = "license_rules.json"  # Assume this file exists
variable_patterns = [
    {'original': 'Copyright (c) 2023', 'variable': 'Copyright (c) [Year]'}
]

# Create a dummy rules file for demonstration
dummy_rules = [{"text": "Copyright (c) 2023, some rights reserved."}]
with open(rules_file, 'w') as f:
    json.dump(dummy_rules, f, indent=4)

update_license_rules(rules_file, variable_patterns)

with open(rules_file, 'r') as f:
    updated_rules = json.load(f)
    print(json.dumps(updated_rules, indent=4))
```

### 3. Post-processing with fuzzy matching for minor variations

```python
from fuzzywuzzy import fuzz

def fuzzy_match_license(detected_text, rule_text, threshold=80):
    """Performs fuzzy matching to handle minor variations."""
    similarity = fuzz.ratio(detected_text, rule_text)
    if similarity >= threshold:
        return True
    return False

# Example usage
detected_text = "Copyright (c) 2023, some rights reserved."
rule_text = "Copyright (c) [Year], some rights reserved."

if fuzzy_match_license(detected_text, rule_text):
    print("License matched with minor variations.")
else:
    print("License did not match.")
```

### 4. Unit test example using pytest

```python
import pytest
from your_module import match_copyright_year

def test_match_copyright_year_valid_year():
    assert match_copyright_year("Copyright (c) 2023") == "Copyright year: 2023"

def test_match_copyright_year_variable_year():
    assert match_copyright_year("Copyright (c) [Year]") == "Year is variable"

def test_match_copyright_year_no_match():
    assert match_copyright_year("This is some text") is None
```

### Approximate schedule

| **Week** | **Date Range** | **Tasks** |
| :------- | :------------- | :---------------------------------------------- |
| Week 1 | 5/8-6/1 | Research and Setup |
| Week 2 | 6/2-6/8 | Design and Rule Analysis |
| Week 3 | 6/9-6/15 | Rule Analysis and Logic Design |
| Week 4 | 6/16-6/22 | Grammar Implementation |
| Week 5 | 6/23-6/29 | Detection Logic Implementation |
| Week 6 | 6/30-7/6 | Unit Testing (Core Functionality) |
| Week 7 | 7/7-7/13 | Post-processing Implementation |
| Week 8 | 7/14-7/20 | Automation Script Development |
| Week 9 | 7/21-7/27 | Unit Testing (Post-processing and Scripts) |
| Week 10 | 7/28-8/3 | Extensive Testing and Bug Fixing |
| Week 11 | 8/4-8/10 | Integration Testing |
| Week 12 | 8/11-8/17 | Documentation and Finalization |
