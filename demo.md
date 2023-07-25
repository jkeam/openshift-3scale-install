# 3scale Demo Script

1. Basics
    1. API
        - main concepts, product and backend
    2. Product
        - the APIs that we will be exposing to our end users
        - rate limiting and policies
2. Product
    - Name: Cat Product
    - Description: Cats for great profit!
3. Backend
    - Integration
        - Name: "Ninja Cats"
        - Private Base URL: "https://catfact.ninja"
        - Add to product
4. Show Endpoints
    - https://catfact.ninja just HTML
    - https://catfact.ninja/facts lots of facts
    - https://catfact.ninja/fact single fact
    - https://catfact.ninja/breeds lots of breeds
5. Methods and Metrics
    1. Add a method
        - Name: Cat Facts
        - Description: Track things related to cat facts.
    2. Add a method
        - Name: Cat Breeds
        - Description: Track things related to cat facts.
    3. Add Mapping Rule - DO FACT FIRST
        - /fact
        - /facts
        - /breeds
6. Application Plans - Rules that govern your usage of the API.
Plans dicate the usage of the API.
    1. Create plan
        - Basic
        - Cat Breeds method limit to 5
    2. Back to application plans -> create plan
        - Gold
        - No limits
    3. Set default plan -> basic
7. Bob wants access
    1. Can create CMS for developer to sign up with or without approval
        - Can create in the portal here (Audience, Developer Portal -- for Echo API)
        - Click Visit Portal
    2. Dropdown -> Audience
        - We're going to do now for this demo
8. Application - Like when you request access to Twitter or Facebook,
you create an application and describe the purpose of your app;
why you need access to the API.
    1. Dropdown: Products -> Listing
    2. Show API key
9. Configuration
    1. Steps
        - Dropdown -> Product -> Cat Product
        - Integration -> Configuration
    2. Lifecycle steps, staging and production
        - You can see the example curl, with Bob's key, since only one in the system
        - And we can hit this we will be bob
10. Testing
    1. curl the /breeds example 5 or so times
    2. view the analytics -> traffic
    3. hit the /facts endpoint
11. Bob wants to upgrade to Gold
    1. Steps - Application -> Listing
    2. Change Plan to Gold - Talk about Gateway and API Manager and it's async as it's being pushed this new plan.
    3. Try /breeds endpoint to see it succeeds
12. Mapping Policy
    1. Hit /jon, demonstrate nothing
    2. Show -vvv to see headers
    3. See Error config - Integration -> Settings to see error configuration
    4. Policies -> URL Rewriting -> COMMANDS
        - GET
        - /jon
        - First substitution
        - /fact
    5. Reorder to get the rewriting to be done first
    6. Integration -> Configuration -> Promote
