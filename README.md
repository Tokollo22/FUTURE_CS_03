# API Security Risk Analysis

**Task 3: API Security Risk Analysis**  

---

## 1. Project Overview

A report to identify the security vulnerabilities in a public API, analyze the risks and provide recommendations to improve security.

**API Tested:** JSONPlaceholder (https://jsonplaceholder.typicode.com)

**Tools Used:**
-Postman
-Browser DevTools (Network Inspector)

---

## 2. Objectives

- Identify **insecure API endpoints** and exposed data  
- Analyze **authentication and authorization** mechanisms  
- Detect **missing rate limiting** or input validation vulnerabilities  
- Explain risks in **simple business-friendly language**  
- Recommend **remediation steps**

---

## 3. Methodology

3.1 **Endpoint Testing**: test all the public endpoints using Postman to retrieve data.  
3.2 **Data Exposure Check**: to return JSON data for sensitive fields like email, phone, or address.  
3.3 **Authentication & Authorization**: Check whether endpoints required API keys or user credentials. Test access to multiple user records to identify broken access control.  
3.4 **Rate Limiting**: Send repeated requests to check if the API implements request limits.  
3.5 **Input Validation**: Sent potentially malicious payloads to detect vulnerabilities such as XSS or injection attacks.  
3.6 **Documentation**: Screenshots and findings were recorded for all tests.


## 4. Findings

| Vulnerability | Risk Level | Description |
|---------------|------------|-------------|
| **No Authentication** | Medium | API allows access to all endpoints without API keys. |
| **Data Exposure** | Low | Sensitive user data such as emails and phone numbers are visible to anyone. |
| **Broken Access Control** | Medium | Any user can access all other user data without restrictions. |
| **No Rate Limiting** | Medium | API allows unlimited requests in which it could lead to abuse or DDoS attacks. |
| **Missing Input Validation** | Medium | API accept potentially malicious input without sanitization. |

---

## 5. Impact

Consequences of the vulnerabilities above:

- **Unauthorized access** to restricted resources
- **leakage** of user information
- **System abuse** due to unlimited requests
- **Injection attacks** from unvalidated input

---

## 6. Recommendations

No Authentication : Implement API keys for all endpoints.
Data Exposure : Restrict sensitive fields so that only authorized users can access them. 
Broken Access Control : Implement proper access controls to restrict access per user roles.
No Rate Limiting : Introduce rate limite to prevent DDoS attacks.
Missing Input Validation : Validate all user inputs in server-side. 

## 7. screenshot

<img width="1365" height="767" alt="users-api-response" src="https://github.com/user-attachments/assets/f9ee82af-ff3c-48b9-9c90-bfd8ab3fd45a" />
<img width="769" height="584" alt="data-exposure" src="https://github.com/user-attachments/assets/6514a8d1-05f9-4b85-8561-fa552d087821" />
<img width="1365" height="767" alt="no-authentication" src="https://github.com/user-attachments/assets/36878435-8378-4c5b-8186-3dc8f587546c" />
<img width="1365" height="767" alt="authorization-test" src="https://github.com/user-attachments/assets/e5169191-fe08-4864-9c1e-c26ba548b156" />
<img width="1102" height="386" alt="rate-limit-test" src="https://github.com/user-attachments/assets/0bfebde4-3fa0-4620-9a0d-7850f42a9fec" />
<img width="1365" height="767" alt="input-validation-test" src="https://github.com/user-attachments/assets/f2a6dfbb-0e4a-4ba6-863d-6f9baa9c7622" />
<img width="1365" height="726" alt="browser-devtools-api" src="https://github.com/user-attachments/assets/7d66f2e9-4e16-45ef-b2dc-9719530112c6" />
