MPIN Strength Analyzer
This project helps check how strong or weak a 4-digit or 6-digit MPIN (Mobile Personal Identification Number) is. It uses simple rules to score the MPIN and tells whether it is strong, moderate, or weak. It also explains why a PIN is considered weak.

Objective:
People often choose PINs that are easy to guess. For example:Common PINs like 1234, 0000
Dates like birthdays or anniversaries
Patterns like repeated or low-variance digits

This project:
Checks if the PIN is commonly used
Compares it with personal information
Uses digit-based features like variance and repetition
Gives a score and strength label

Scoring Rules
Rule Type	Reason Code	Score Added	Strength Result
Common PIN	COMMONLY_USED	+5	Weak
Date of Birth	DEMOGRAPHIC_DOB	+5	Weak
Spouse Birthday	DEMOGRAPHIC_SPOUSE	+5	Weak
Anniversary	DEMOGRAPHIC_ANNIVERSARY	+5	Weak
Child’s Birthday	DEMOGRAPHIC_CHILD	+3	Weak
Pet’s Birthday	DEMOGRAPHIC_PET	+3	Weak
Repeated Digits	REPEATED_DIGITS	+1	Moderate
Low Uniqueness	LOW_UNIQUENESS	+1	Moderate
Low Digit Variance	LOW_VARIANCE	+1	Moderate
4-digit PIN	SHORT_PIN	+1	Moderate

Final Strength Based on Score:
Strong: score 0–2
Moderate: score 3–5
Weak: score above 5

What the Dataset Contains
The dataset has the following columns:
pin: 4 or 6 digit number
dob, spouse_dob, anniversary, child_dob, pet_dob: user’s personal dates
After scoring, we also get:
score: total score of the pin
strength: strong, moderate, or weak
reasons: list of reasons if the pin is weak

Features Used
PIN length (4 or 6)
Digit variance
Maximum repeated digit count
Number of unique digits
Match with personal dates