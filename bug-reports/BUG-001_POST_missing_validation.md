# BUG-001 — POST /users Accepts Request Without Body

**Reported By:** Mahaya Zeb Khan  
**Date:** 09 March 2026  
**Tool:** Postman  
**Severity:** Medium  
**Priority:** High  
**Status:** Open  

---

## Summary
POST /users endpoint accepts requests with no request body 
and returns 201 Created instead of rejecting with 400 Bad Request.

---

## Environment
- API: JSONPlaceholder
- URL: https://jsonplaceholder.typicode.com/users
- Method: POST
- Tool: Postman

---

## Steps to Reproduce
1. Open Postman
2. Set method to POST
3. Set URL to https://jsonplaceholder.typicode.com/users
4. Do NOT add any request body
5. Click Send

---

## Expected Result
400 Bad Request — required fields missing.
API should validate that name and email are provided.

---

## Actual Result
201 Created — user created successfully with empty body.
Response returns: {}

---

## Impact
Users can be created without any required data.
This could cause:
- Empty or corrupt records in database
- Downstream failures in systems expecting valid user data
- Data integrity issues

---

## Evidence
screenshots/POST_no_body_201.png

---

## Recommendation
API should validate required fields before creating resource.
Return 400 Bad Request with clear error message when 
required fields are missing.