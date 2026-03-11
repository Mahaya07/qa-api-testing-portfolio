# BUG-002 — DELETE /users/1 Does Not Persist Deletion

**Reported By:** Mahaya Zeb Khan  
**Date:** 09 March 2026  
**Tool:** Postman  
**Severity:** High  
**Priority:** High  
**Status:** Open  

---

## Summary
DELETE /users/1 returns 200 OK confirming deletion but 
subsequent GET /users/1 still returns the user data.
Deletion is not persisting in the database.

---

## Environment
- API: JSONPlaceholder
- URL: https://jsonplaceholder.typicode.com/users/1
- Method: DELETE then GET
- Tool: Postman

---

## Steps to Reproduce
1. Open Postman
2. Set method to DELETE
3. Set URL to https://jsonplaceholder.typicode.com/users/1
4. Click Send — note 200 OK response
5. Change method to GET
6. Set URL to https://jsonplaceholder.typicode.com/users/1
7. Click Send

---

## Expected Result
Step 4: 200 OK — deletion confirmed
Step 7: 404 Not Found — user no longer exists

---

## Actual Result
Step 4: 200 OK — deletion confirmed
Step 7: 200 OK — user still returned as if never deleted

---

## Impact
Deleted records are still accessible after deletion.
This could cause:
- Security risk — deleted user data still accessible
- Data integrity issues — system shows deleted records
- Incorrect application behaviour after deletion
- Failed audit trails for compliance requirements

---

## Evidence
- screenshots/DELETE_user_200.png
- screenshots/GET_after_delete_verification.png

---

## Recommendation
DELETE operation should persist to database.
Subsequent GET on deleted resource should return 404 Not Found.
This is standard REST API behaviour and must be implemented
for data integrity and security compliance.