# 30Days30APISecurityTests

## Test 1 : BOLA by changing auth token

1. Get attacker auth token 
2. Add it in dashboard 
3. Select endpoint in the inventory (PATCH reviews)
4. Review the payload once.
5. Look at the original review (this is the original review)
6. Run test by selecting one BOLA case - BOLA by changing auth token
7. Look at the test results - API is vulnerable
8. Test result and attack attempt
9. Look at the edited review on the dashboard (some review edited for the first time)


https://user-images.githubusercontent.com/91306853/217299424-6736d728-6803-4134-8c97-225193bf7698.mp4

## Test 2 : Broken Function Level Authorization by changing HTTP Method

1. Open the API collection that you want to test for vulnerabilities.
2. Click on Run test button.
3. Select only Broken Function level authorization by changing HTTP method test.
4. Count to 10-Mississippi for Test results.
5. Analyze the High severity issues. 
6. Here, we selected the /api/cards endpoint that fetches all the credit card info from all users.

https://user-images.githubusercontent.com/91306853/217300011-db834337-70d2-4985-926e-0970e7f8e78e.mp4

## Test 3 : Broken user authentication by removing auth token

1. Set attacker token
2. Observe api (Feedbacks endpoint in this case)
3. Select this endpoint
4. Click on Run test with just Broken Auth
5. Wait for test result
6. Check original attempt has auth token
7. Test attempt doesn't have token, yet it succeeded - Broken user authentication vulnerability found. :key:


https://user-images.githubusercontent.com/91306853/219386085-820ef832-3679-4d2c-9a7f-6af499923d21.mov

## Test 4 : Swagger file detection - Security misconfiguration 

1. Click on run and select swagger file detection test
2. Go to testing and wait for a minute for test results
3. Click on the failed test - Assets found on page
4. Click on the Attempt tab to see the test API call
5. The response contains HTML page with swagger details
6. Verify it by actually entering the URL

🐞 Detected unprotected swagger file!


https://user-images.githubusercontent.com/91306853/221205469-12081044-f357-457c-a18e-0582dd4ba256.mp4



## Test 5 : JWT None algo attack

1. Look at the original data - last name is "johnson"
2. Select the endpoint you want to test for JWT None attack
3. Click on Run test and select JWT None algo attack
4. Look at the test results - 1 HIGH severity issue found
5. Akto made 4 attempts - 1 succeeded with 200 OK 
6. Refresh website, notice lastname changed from "johnson" to "victim"
7. Look at the attack again, check the token on http://JWT.io
8. Observe algo=none

🐞 JWT None algo vulnerability found




https://user-images.githubusercontent.com/91306853/221206399-5b6f856b-e56c-4fe8-926a-bdb48136845d.mp4






## Test 6 : JWT failed to verify signature test

1. Select a POST order endpoint
2. Select the Broken Authentication test - JWT failed to verify signature
3. Go to test results. Observe that there is a high vulnerability issue
4. Check the Original tab - the original token signature starts with "HQq0"
5. Check Attempt tab - gives 200 OK response with signature starting with "aQq0" - this is invalid signature, yet server accepted



https://user-images.githubusercontent.com/91306853/221205245-6c32c6d3-2863-4db7-aacf-fa0868f19970.mp4






## Test 7 : Broken Object Level Authorization by Parameter Pollution 

1. Select BOLA by parameter pollution
2. Run test.
3. Check results
4. The original request has 3 params.
5. Attempt request has 6 params - all occurring twice with a diff "BasketId" value. 
6. This results in a success response
7. The victim's cart has a new product added now!

🐞 Vulnerable API


https://user-images.githubusercontent.com/91306853/221206568-3d3d75f2-1e69-4d0d-86a2-8c98cb87bb7d.mp4



## Test 8 : Broken Object Level Authorization in old API versions


1. Select the list of endpoints
2. Select Old version API tests.
3. Go to the test results section
4. Check details for the vulnerability
5. Notice that original endpoint uses v2 - /api/v2/users
6. Navigate to Attempt tab
7. Notice that /api/v1/users also returns 200 OK with the flag

🐞 BOLA in old api versions



https://user-images.githubusercontent.com/91306853/221204869-5b191e29-9748-4e10-99e3-6c401569717f.mp4



## Test 9 : Security misconfiguration - django-exposed-debug-page 

1. Select the Django-exposed-debug-page test and run it
2. Wait for the result
3. Check the Attempt tab and look for debug details in the response
4. Check details for the vulnerability
5. Observe we open the debug page - with details of modules, and inner workings of Django server code

🐞 django-exposed-debug-page


https://user-images.githubusercontent.com/91306853/221204724-bb78be9a-378b-4456-a9f6-212b198f7893.mp4




## Test 10 : Security misconfiguration - Open redirects

1. Select the API Collection you want to test
2. Select Open-redirect test under Security Misconfiguration and click on run test
3. Navigate to testing. Notice, Akto has found all the APIs which have open redirects
4. Click on the vulnerability to see details.
5. Notice that the original request redirects to GitHub
6. Navigate to Attempt tab. Notice Akto tries a test to redirect to evil. com
7. See the attempt succeeds! Server returns 302 with location evil. com. 

🐞 API is vulnerable!



Uploading Open redirects (1).mp4…


