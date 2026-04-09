# API Security Risk Analysis – JSONPlaceholder

**Author:** ANIKA TALAVADEKAR  
**Internship Task:** Future Interns – API Security Risk Analysis (2026)  
**Date:** 09-Apr-2026  

---

## Overview

This repository contains a comprehensive **API Security Risk Analysis** conducted on the public demo API [JSONPlaceholder](https://jsonplaceholder.typicode.com).  

The purpose of this assessment was to evaluate **API security posture**, identify potential vulnerabilities, and provide actionable recommendations — similar to what professional SaaS security consultants deliver for real-world clients.

---

## Objectives

- Assess API endpoints for **authentication and authorization weaknesses**  
- Identify potential **data exposure risks**  
- Review **security headers and input handling**  
- Provide **clear remediation guidance** in business-friendly language  

---

## Tools & Environment

- **Postman** (Browser & Desktop Agent) – For sending requests and inspecting responses  
- **Kali Linux** – Testing environment  
- **Google Docs / MS Word** – For report preparation and documentation  

---

## Methodology

1. Selected JSONPlaceholder API as the target.  
2. Reviewed API documentation and endpoint structure.  
3. Tested key endpoints using Postman:  
   - `GET /users`  
   - `GET /users/1`  
   - `GET /users/2`  
   - `POST /posts`  
   - `GET /posts?userId=1` (Query filtering)  
4. Inspected response headers, authentication requirements, and data exposure.  
5. Classified risks by severity (Low / Medium / High).  
6. Prepared evidence and actionable remediation recommendations.  

---

## Key Findings

1. **No Authentication** – High  
   - API endpoints are accessible without authentication, exposing user data.  

2. **Broken Authorization** – High  
   - Accessing other users’ data is possible without proper authorization.  

3. **Unauthenticated Data Creation** – High  
   - POST requests allow creation of resources without authentication (`id: 201`).  

4. **Missing Security Headers** – Medium  
   - Key headers like `Content-Security-Policy` and `Strict-Transport-Security` are absent.  

5. **Weak Input Validation** – Medium  
   - Query parameters are not validated or sanitized, creating potential risks in production.  

*(Detailed evidence and screenshots are included in the repository.)*  

---

## Repository Contents

- `API_Security_Risk_Analysis_Report.pdf` – Full report with findings and recommendations  
- `screenshots/` – Folder containing Postman request screenshots:  
  - `users_endpoint.png`  
  - `single_user.png`  
  - `user2_access.png`  
  - `post_request.png`  
  - `headers.png`  
  - `filtered_posts.png`  

---

## Recommendations

1. Implement **authentication** (JWT / API Key) for all sensitive endpoints.  
2. Enforce **authorization checks** per user and role.  
3. Require authentication for **POST / PUT / DELETE** operations.  
4. Add **security headers** to API responses.  
5. Validate and sanitize **all user inputs**.  
6. Implement **rate limiting** to prevent abuse.  

---

## Conclusion

This assessment demonstrates real-world API security practices. Although JSONPlaceholder is a demo API, the findings highlight risks that would be **critical in production environments**.  

This repository showcases **risk identification, evidence collection, and remediation planning**, illustrating the skills expected from a modern SaaS security consultant.
