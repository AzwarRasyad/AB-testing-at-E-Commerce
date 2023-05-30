# AB-testing-at-E-Commerce

# Project Description

You've received an analytical task from an international online store. Your predecessor failed to complete it: they launched an A/B test and then quit (to start a watermelon farm in Brazil). They left only the technical specifications and the test results.

# Technical description

- Test name: `recommender_system_test`
- Groups: А (control), B (new payment funnel)
- Launch date: 07-12-2020
- The date when they stopped taking up new users: 21-12-2020
- End date: 01-01-2021
- Audience: 15% of the new users from the EU region
- Purpose of the test: testing changes related to the introduction of an improved recommendation system
- Expected result: within 14 days of signing up, users will show better conversion into product page views (the `product_page` event), product card views (`product_card`) and purchases (`purchase`). At each of the stage of the funnel `product_page → product_card → purchase`, there will be at least a 10% increase.
- Expected number of test participants: 6000

# Description of the data

- `ab_project_marketing_events_us.csv` — the calendar of marketing events for 2020
- `final_ab_new_users_upd_us.csv` — all users who signed up in the online store from December 7 to 21, 2020
- `final_ab_events_upd_us.csv` — all events of the new users within the period from December 7, 2020 to January 1, 2021
- `final_ab_participants_upd_us.csv` — table containing test participants

Structure of `ab_project__marketing_events_us.csv`:

- `name` — the name of the marketing event
- `regions` — regions where the ad campaign will be held
- `start_dt` — campaign start date
- `finish_dt` — campaign end date

Structure of `final_ab_new_users_upd_us.csv`:

- `user_id`
- `first_date` — sign-up date
- `region`
- `device` — device used to sign up

Structure of `final_ab_events_upd_us.csv`:

- `user_id`
- `event_dt` — event date and time
- `event_name` — event type name
- `details` — additional data on the event (for instance, the order total in USD for `purchase` events)

Structure of `final_ab_participants_upd_us.csv`:

- `user_id`
- `ab_test` — test name
- `group` — the test group the user belonged to

# Project Instruction

- Describe the goals of the study.
- Explore the data:

    - Do types need to be converted?
    - Are there any missing or duplicate values? If so, what are they like?

- Carry out exploratory data analysis:

    - Study conversion at different stages of the funnel.
    - Is the number of events per user distributed equally among the samples?
    - Are there users who are present in both samples? 
    - How is the number of events distributed among days?
    - Are there any peculiarities in the data that you have to take into account before starting the A/B test?

- Evaluate the A/B test results:

    - What can you say about the A/B test results?
    - Use a z-test to check the statistical difference between the proportions.

- Describe your conclusions regarding the EDA stage and the A/B test results.
