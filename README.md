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

