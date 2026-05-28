AI Security Vulnerability Scanning Lab




This project demonstrates how to identify and analyze security vulnerabilities in AI/ML code using four complementary tools:

Bandit — Python static analysis

Semgrep — pattern‑based SAST

Pylint — code quality and correctness

Safety — dependency vulnerability scanning

The repository includes intentionally vulnerable demo scripts that showcase common AI/ML security weaknesses such as unsafe deserialization, data poisoning, and model extraction.

📁 Project Structure
Code
ai-security-lab/
│
├── demo_code_1.py
├── demo_code_2.py
│
└── security-reports/
    ├── bandit.json
    ├── semgrep.json
    ├── pylint-results.txt
    └── safety.json
🎯 Objectives
This lab demonstrates how to:

Detect insecure Python patterns using Bandit

Identify ML‑specific risks using Semgrep

Improve maintainability with Pylint

Scan dependencies for CVEs using Safety

Compare tool behaviors and understand why results differ

Map findings to CWE categories for security reporting

🛡️ Tools and What They Found
1. Bandit — Python Static Analysis




Bandit scanned the project files and reported:

0 HIGH

2 MEDIUM

9 LOW

Although the code contains high‑impact vulnerabilities (unsafe pickle.load(), arbitrary code execution, OS command execution), Bandit classified them as MEDIUM/LOW because the malicious behavior is intentional and not user‑controlled.

Earlier scans that included the virtual environment produced thousands of findings — these came from third‑party packages, not the project code.

2. Semgrep — Pattern‑Based SAST
Semgrep identified 4 blocking findings, all related to unsafe pickle deserialization:

Rule: python.lang.security.deserialization.pickle.avoid-pickle

Semgrep flags risky patterns regardless of context, making it highly effective for ML‑specific vulnerabilities.

3. Pylint — Code Quality




Pylint reported warnings and errors related to:

unused imports

unused variables

stylistic issues

These findings improve maintainability and reduce the likelihood of future vulnerabilities.

4. Safety — Dependency Vulnerability Scanning




Safety reported:

0 vulnerable packages

This confirms that the environment did not contain known CVEs.

📊 Consolidated Findings
Tool	Strength	Findings	Notes
Bandit	Context‑aware static analysis	2 MEDIUM, 9 LOW	Downgrades intentional demo vulnerabilities
Semgrep	Pattern‑based detection	4 blocking	Flags all unsafe pickle usage
Pylint	Code quality	Several W/E	Non‑security but important
Safety	Supply chain security	0 CVEs	Clean dependency set


🔐 Key Security Concepts Demonstrated
Unsafe deserialization (CWE‑502)

Arbitrary code execution (CWE‑94)

OS command injection (CWE‑78)

Model extraction (CWE‑200)

Data poisoning (CWE‑20)

These vulnerabilities are intentionally included for educational purposes.

📘 Summary
This lab demonstrates that no single tool provides complete coverage.
Bandit excels at identifying insecure Python patterns in realistic contexts, Semgrep reliably detects dangerous constructs, Pylint improves code robustness, and Safety ensures supply‑chain integrity.

Together, these tools provide a strong foundation for securing AI/ML systems before deployment.

If you want, I can also generate a CWE‑mapped vulnerability table or a final lab conclusion paragraph to complete your submission.

Generate lab README
Here it is, Eric — a clean, polished, GitHub‑ready README for your AI Security Lab project.
It’s structured for clarity, professionalism, and portfolio value, and it reflects exactly what your scans revealed.

AI Security Vulnerability Scanning Lab



This lab demonstrates how to identify and analyze security vulnerabilities in AI/ML code using four complementary tools:

Bandit — Python static analysis

Semgrep — pattern‑based SAST

Pylint — code quality and correctness

Safety — dependency vulnerability scanning

The repository includes intentionally vulnerable demo scripts that showcase common AI/ML security weaknesses such as unsafe deserialization, model extraction, and data poisoning.

📁 Project Structure
Code
ai-security-lab/
│
├── demo_code_1.py
├── demo_code_2.py
│
└── security-reports/
    ├── bandit.json
    ├── semgrep.json
    ├── pylint-results.txt
    └── safety.json
🎯 Objectives
This lab demonstrates how to:

Detect insecure Python patterns using Bandit

Identify ML‑specific risks using Semgrep

Improve maintainability with Pylint

Scan dependencies for CVEs using Safety

Compare tool behaviors and understand why results differ

Map findings to CWE categories for security reporting

🛡️ Tool Results Overview
1. Bandit — Python Static Analysis
Bandit scanned the project files and reported:

0 HIGH

2 MEDIUM

9 LOW

Although the code intentionally contains high‑impact vulnerabilities (unsafe pickle.load(), arbitrary code execution, OS command execution), Bandit classified them as MEDIUM/LOW because the malicious behavior is intentional and not user‑controlled.

Earlier scans that included the virtual environment produced thousands of findings — these came from third‑party packages, not the project code.

2. Semgrep — Pattern‑Based SAST
Semgrep identified 4 blocking findings, all related to unsafe pickle deserialization:

Rule: python.lang.security.deserialization.pickle.avoid-pickle

Semgrep flags risky patterns regardless of context, making it highly effective for ML‑specific vulnerabilities.

3. Pylint — Code Quality
Pylint reported warnings and errors related to:

unused imports

unused variables

stylistic issues

These findings improve maintainability and reduce the likelihood of future vulnerabilities.

4. Safety — Dependency Vulnerability Scanning
Safety reported:

0 vulnerable packages

This confirms that the environment did not contain known CVEs.

📊 Consolidated Findings
Tool	Strength	Findings	Notes
Bandit	Context‑aware static analysis	2 MEDIUM, 9 LOW	Downgrades intentional demo vulnerabilities
Semgrep	Pattern‑based detection	4 blocking	Flags all unsafe pickle usage
Pylint	Code quality	Several W/E	Non‑security but important
Safety	Supply chain security	0 CVEs	Clean dependency set


🔐 Key Security Concepts Demonstrated
Unsafe deserialization (CWE‑502)

Arbitrary code execution (CWE‑94)

OS command injection (CWE‑78)

Model extraction (CWE‑200)

Data poisoning (CWE‑20)

These vulnerabilities are intentionally included for educational purposes.

📘 Summary
This lab demonstrates that no single tool provides complete coverage.
Bandit excels at identifying insecure Python patterns in realistic contexts, Semgrep reliably detects dangerous constructs, Pylint improves code robustness, and Safety ensures supply‑chain integrity.

Together, these tools provide a strong foundation for securing AI/ML systems before deployment.
