# Social Network - System Design

Homework project for [course by System Design](https://balun.courses/courses/system_design). Social Network for the travelers.

### Functional requirements:

- posts publication with photos, description and geotag
- other travelers posts commenting and rating
- subscription to travelers to track their activity
- popular places search and location's posts listing
- other travelers feed view

### Non-functional requirements:

#### General

- 10 000 000 DAU
- availability 99,95%
- CIS region only
- web and mobile applications
- the workload depends on the holiday season
- response time limit ~ 1s
- user is online 12 hours daily (1/2 day)

#### Posts

> Write: ~120 RPS \
> Read: ~7000 RPS

- User publishes 1 post every day, the post has:
  - At most 5 photos, max photo size is 3mb
  - At most 256 letters description
  - Geotag
- User views 10 posts in the feed every 2 hours when online (6 times daily)

#### Reactions

> Write: ~7000*0,8 = ~5600 RPS \
> Read: ~7000 RPS (as the posts read)

- User views the reactions for the every seen post
- User reacts to the 80% of the viewed posts
  - Total viewed posts by the user daily = 60 as in the Posts block 

#### Subscription

> Write: ~120 RPS \
> Read: ~700 RPS

- User subscribes to 1 other user every day
- User checks his subscriptions every 2 hours when online (6 times daily)

#### Search

> Read: ~350 RPS

- User searches new places 2-4 times every day
  - User checks first 20 posts for the queries place
