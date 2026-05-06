## Fakestore API Bug Report

| Bug ID | API Name | Bug Title | Description | Steps to Reproduce | Expected Result | Actual Result | Severity | Priority | Status |
|:-------|:---------|:----------|:------------|:-------------------|:----------------|:--------------|:---------|:---------|:-------|
| BUG_001 | GET /products/{id} | 200 OK for invalid ID | API returns success for non-existent product ID. | 1. Open Postman <br> 2. GET /products/9999 | 404 Not Found | 200 OK with empty response | Low | Medium | Open |
| BUG_002 | GET /products/{id} | 200 OK for non-numeric ID | API returns success for non-numeric product ID. | 1. Open Postman <br> 2. GET /products/whoami | 404 Not Found | 200 OK with empty response | Low | Medium | Open |
| BUG_003 | GET /carts/{id} | 200 OK for invalid cart ID | API returns success with NULL body for invalid cart ID. | 1. Open Postman <br> 2. GET /carts/{invalid_id} | 404 Not Found | 200 OK with NULL response | Low | Medium | Open |
| BUG_004 | GET /users/{id} | 200 OK for invalid user ID | API returns success with NULL body for invalid user ID. | 1. Open Postman <br> 2. GET /users/{invalid_id} | 404 Not Found | 200 OK with NULL response | Low | Medium | Open |
| BUG_005 | POST /carts | 201 Created for empty userId | API creates cart even if userId field is missing. | 1. Open Postman <br> 2. POST /carts (missing userId) | 400 Bad Request with error | 201 Created; no error message | High | High | Open |
| BUG_006 | POST /carts | 201 Created for empty products | API creates cart even if products field is empty. | 1. Open Postman <br> 2. POST /carts (empty products) | 400 Bad Request with error | 201 Created; no error message | Medium | High | Open |
