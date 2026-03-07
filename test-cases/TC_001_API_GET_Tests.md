# Test Cases — GET API Tests
**API:** JSONPlaceholder (https://jsonplaceholder.typicode.com)  
**Tester:** Mahaya Zeb Khan  
**Date:** 08 March 2026  
**Tool:** Postman  

---

## TC-001 | Get All Users

| Field | Details |
|-------|---------|
| **Test ID** | TC-001 |
| **Title** | GET all users returns 200 with complete list |
| **Method** | GET |
| **URL** | /users |
| **Precondition** | API is accessible |
| **Steps** | Send GET request to /users |
| **Expected Result** | 200 OK, returns list of 10 users |
| **Actual Result** | 200 OK, returned 10 users |
| **Status** | ✅ PASS |
| **Evidence** | screenshots/GET_all_users_200OK.png |

---

## TC-002 | Get Single User

| Field | Details |
|-------|---------|
| **Test ID** | TC-002 |
| **Title** | GET single user by valid ID returns correct data |
| **Method** | GET |
| **URL** | /users/1 |
| **Precondition** | User with ID 1 exists |
| **Steps** | Send GET request to /users/1 |
| **Expected Result** | 200 OK, returns user Leanne Graham |
| **Actual Result** | 200 OK, returned Leanne Graham |
| **Status** | ✅ PASS |
| **Evidence** | screenshots/GET_single_user_200OK.png |

---

## TC-003 | Get Non-Existent User (Negative Test)

| Field | Details |
|-------|---------|
| **Test ID** | TC-003 |
| **Title** | GET user with invalid ID returns 404 |
| **Method** | GET |
| **URL** | /users/999 |
| **Precondition** | User ID 999 does not exist |
| **Steps** | Send GET request to /users/999 |
| **Expected Result** | 404 Not Found with error message |
| **Actual Result** | 404 Not Found, empty response body {} |
| **Status** | ⚠️ PARTIAL PASS |
| **Observation** | API returns empty {} instead of descriptive error message. Good APIs should return meaningful error details. |
| **Evidence** | screenshots/GET_invalid_user_404.png |

---

## TC-004 | Get All Posts

| Field | Details |
|-------|---------|
| **Test ID** | TC-004 |
| **Title** | GET all posts returns 200 with 100 records |
| **Method** | GET |
| **URL** | /posts |
| **Precondition** | API is accessible |
| **Steps** | Send GET request to /posts |
| **Expected Result** | 200 OK, returns 100 posts |
| **Actual Result** | 200 OK, returned 100 posts |
| **Status** | ✅ PASS |
| **Evidence** | screenshots/GET_all_posts_200OK.png |

---

## 📊 Execution Summary

| Total | Passed | Partial | Failed | Pass Rate |
|-------|--------|---------|--------|-----------|
| 4 | 3 | 1 | 0 | 75% Full Pass / 100% No Failures |
```

**Save → Ctrl + S**

---

## Now Push Everything to GitHub!

Go to Command Prompt and type one by one:
```
git add .
```
```
git commit -m "Add TC-001 to TC-004: GET API test cases with evidence"
```
```
git push