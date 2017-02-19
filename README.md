# trumpsterm

Tweets from @trumpterm

## Setup

1. Clone this repository.
2. Create a Twitter app under your Twitter account.
2. Set configuration variables to the app's credentials:
```heroku config:set CONSUMER_KEY=X CONSUMER_SECRET=Y ACCESS_TOKEN=Z ACCESS_TOKEN_SECRET=A```
3. Deploy to Heroku.
4. Set up a scheduler to `rake tweet` at whatever frequency you'd like.