Recognizing Cyber Threats Using Simple AI Rules

## Overview
This assignment explores the use of a simple, rule-based Artificial Intelligence (AI) system to identify and classify common cyber threats such as Phishing, Malware, and Ransomware from text messages. The system operates by scanning messages for predefined keywords associated with each threat category, providing a transparent and interpretable method for threat detection.

## Dataset
The analysis is performed on a dataset named `simple_cyber_messages.csv`, which contains a collection of messages, their `message_id`, and `correct_category` (the ground truth classification of the threat).

## Methodology

### 1. Manual Threat Identification (Q1)
Initially, a small subset of messages (the first 10) is manually reviewed to understand the nature of the threats and identify important keywords or phrases indicative of specific cyber-threat categories. This step helps in building intuition for the subsequent rule-based approach.

### 2. Keyword Lists and Rule-Based Classifier (Q2)
A core component of this assignment is the `RULE_KEYWORDS` dictionary, which defines lists of keywords for 'Phishing', 'Malware', and 'Ransomware'. A `classify_message` function is implemented to:
- Convert incoming messages to lowercase.
- Count the occurrences of keywords from each category within the message.
- Assign the message to the category with the highest keyword count.
- If no keywords are found, the message is classified as 'Safe'.

The classifier's functionality is demonstrated with several test messages.

### 3. Complete Dataset Classification and Accuracy (Q3)
The `classify_message` function is applied to the entire dataset to predict the category for every message. The predictions are then compared against the `correct_category` to calculate the accuracy of the rule-based system. Key metrics like correct predictions, incorrect predictions, and overall accuracy are displayed.

### 4. Risk Level and Recommended Action (Q4)
Based on the predicted category and the `keyword_score` (number of matched keywords), a `risk_level` (Low, Medium, High) and `recommended_action` are assigned to each message. This step provides practical guidance for handling identified threats.

Additionally, a bar chart visualizes the distribution of predicted message categories across the dataset, offering an overview of the types of threats detected.

### 5. Responsible Use and Reflection (Q5)
This section emphasizes the ethical considerations and limitations of using AI rules for threat detection. It covers important points such as privacy, potential biases in keyword lists, the possibility of false alarms, the need for human accountability, and the importance of human review for high-risk or ambiguous cases.

### Live/New Message Demonstration
To showcase the system's real-world applicability, a new message is fed into the `classify_message` function, and its predicted category, matched keywords, and score are displayed.

### Saving Final Results
The DataFrame containing the original messages, predicted categories, matched keywords, keyword scores, correctness, risk levels, and recommended actions is saved to a CSV file named `Lab1_Final_Result.csv`.

## Key Findings
- The rule-based classifier achieved an impressive accuracy of **96.43%** on the provided dataset, correctly identifying 27 out of 28 messages.
- The single misclassification highlighted a limitation: keyword-based systems can struggle with variations in language or novel phrasing not covered by the predefined keyword lists.
- Phishing messages were often identified by terms like 'urgent', 'verify', 'password', 'OTP', 'bank', 'login', and 'click here'.
- Malware indicators included 'executable', 'trojan', 'spyware', 'attachment', and 'infected'.
- Ransomware messages commonly featured 'encrypted', 'ransom', 'bitcoin', 'restore files', and 'locked files'.
- Messages lacking specific threat-related keywords were classified as 'Safe'.
- Risk levels were dynamically assigned, providing actionable insights.
- The assignment concludes that while effective, such keyword-driven systems are best used as a supportive tool alongside human analysts, emphasizing the necessity of human oversight for sensitive cybersecurity communications.

## How to Run
To execute this notebook, simply run all the code cells sequentially in a Google Colab environment. Ensure the `simple_cyber_messages.csv` file is accessible in the working directory.
