# UN.010.013 Functional Regression [Candidate Applications]: Valid student ID format rejected by application form validator

**Bug Report ID:** BUG-001  
**Feature Module:** Candidate Applications  
**Tester:** [Your Name / Team Name]

---

### [Summary]
The student ID input field within the File Certificate of Candidacy form incorrectly rejects valid ID formats (e.g., "23-1-01032"). The regex or string boundary validation logic appears to evaluate the character length or prefix sequence incorrectly. It throws a false validation error stating that IDs must not exceed the "26-x-xxxxxx" pattern threshold, thereby locking out valid upperclassmen/irregular students from applying.

---

### [Precondition]
* **Software version:** UN.010.013  
* **Software configuration:** Live Vercel Deployment  
* **Hardware specifications:** N/A  
* **Network configuration:** Online (works offline for local deployment)

---

### [Steps to reproduce]
1. Navigate to the Candidate Application section of an election and apply as a candidate.
2. Fulfill the preliminary questions and pass the SEB candidate qualification criteria.
3. Locate the "Student ID Number" input field and enter the valid ID string: `23-1-01032`.
4. Press enter on the input field or click the "Submit Application" button.

---

### [Actual results]
The form submission is blocked. An error message appears beneath the field reading: "First two digits cannot exceed 26."

---

### [Expected results]
The validation should process "23-1-01032" as a valid input. The upper boundary check should gracefully pass any ID prefixes lower than or equal to 26 (e.g., 23, 24, 25). The field should clear validation and allow the user to advance to the file uploads window.

---

### [Additional information]
See attached screenshot from `image_d58935.png`:

![Student ID Validation Error](ca_bug.png)

---

### [Is this Breakage?]
* [X] Yes, see previous code tested  
* [ ] No, new implementation  
* [ ] No, missed from previous pass  

**Previous code tested:** UN.010.013

---

### [Metrics & Impact Assessments]

* **[Severity: How does this problem impact the customer/user?]**  
  `10` - Device or software no longer usable / User cannot proceed to the next part.

* **[Likelihood: How often will a customer/user use this feature/function?]**  
  `8` - High, function is used frequently / All candidate users will experience this.

* **[Repeatability: Is this problem easily reproducible?]**  
  `10` - 100% Reproducible.

> **Risk Priority Number (RPN Calculation):**  
> $RPN = Severity \times Likelihood \times Repeatability$  
> $RPN = 10 \times 8 \times 10 = 800$

* **[Impacted Test Cases]:** CANAPP-0001: Candidate Application Testing - Create  
* **[Impact Sizing (in days)]:** Less than a day
