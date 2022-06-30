# cat-pics
Resources for Tweeting cat pictures.

## Tutorial: Tweeting Media with v2 of the Twitter API in Python
With the launch of the manage Tweets endpoint, we included the ability to attach previously uploaded media to a Tweet. In addition, based on feedback we’ve heard from you, we recently added access to the v1 media endpoints for all users.  

Code that corresponds to [this tutorial](https://developer.twitter.com/en/docs/tutorials/tweeting-media-v2). Code can be found in the folder `v2-media-tutorial` in this repository.

This tutorial will walk you through how to Tweet images of cats using the manage Tweets endpoint of v2 and the v1.1 media endpoints in Python using Flask. Using OAuth 2.0. Authorization Code Flow with PKCE to request the Manage Tweets endpoint requires a user to log in. Therefore, you can use Flask as a web framework to parse the information dynamically.

### Before you start
Before you start, you must install the required packages for this script, including `requests` for making HTTP requests to various endpoints, `tweepy` for working with OAuth 1.0a, `requests_oauthlib` for working with OAuth 2.0, and flask as a web framework.

```python
pip install requests tweepy requests_oauthlib flask
```

In your terminal, you will want to define the following environment variables:

```
export CLIENT_ID=’xxxxxxxxxxxxxx’
export CLIENT_SECRET=’xxxxxxxxxxx’
export REDIRECT_URI=’http://127.0.0.1:5000/oauth/callback’
export API_KEY=’xxxxxxxxxxxxxx’
export API_SECRET=’xxxxxxxxxxx’
export ACCESS_TOKEN=’xxxxxxxxxxx’
export ACCESS_TOKEN_SECRET=’xxxxxxxxxxx’
```

You can obtain your own OAuth 2.0 Client ID and Secret inside of the developer settings in the developer portal.

You will want to use your own credentials found in the [Developer Portal](https://developer.twitter.com/en/portal/dashboard) instead of of the value `xxxxxxxxxxxxxx`.

## Factual cat image support
[@FactualCat](https://twitter.com/FactualCat) is a bot that Tweets cat facts and now images using the code in the folder `factual-cat-image-support`. You will need to run `gsd.py` once locally to log in. After that you can use `every_other.py` to Tweet regularly.

This code is currently deployed to [Render](https://twitter.com/FactualCat) using [redis](https://render.com/docs/redis) and a [cron job](https://render.com/docs/cronjobs) to run twice daily.
