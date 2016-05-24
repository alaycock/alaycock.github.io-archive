---
layout: post
title:  "How to get a free Stripe t-shirt, AKA stop exposing your API keys"
date:   2016-05-23 19:00:00
categories: blog
---

I'm probably preaching to the choir with this post, but it should be pretty obvious that if you ever commit one of your secret API keys to your git repository and push it, you should reset that key.

![](/img/20160523/computer.jpg)

It doesn't matter how long it was exposed, or if you removed it in your next commit, or even if you modified your git history and force pushed it to Github, it still needs to be reset. Your git repository is private? You should probably still reset that key, repositories can get leaked, compromised, or open sourced and  someone could then access your stripe account instead of just your codebase.

I found a number of exposed keys on Github the other day and reported them to Stripe, and after I reported the keys I was offered a free Stripe t-shirt. I'm always one for swag and helping others resolve security issues, so here's how to find some exposed keys for yourself.

![](/img/20160523/shirt.jpg)

1. Find some example code that people might base their project off of, [here's an example from stripe](https://github.com/stripe/monospace-rails/blob/master/config/initializers/stripe.rb). Snag that variable name, and search Github for that.

2. [16,000+ code search results](https://github.com/search?q=Stripe.api_key&type=Code&utf8=%E2%9C%93). The key probably isn't visible right in the results, so open up some of those repos and hit the 'history' button for the file.

3. Go through the [file's history](https://github.com/stripe/monospace-rails/commits/8d8c9ff56755a51a8d58adc76f0c6e3bff828979/config/initializers/stripe.rb) and see check if there are keys in there. Don't forget to trace a little bit through `.env` and other config files.

4. When you find a key, fire off a [curl request to an API endpoint](https://stripe.com/docs/api#balance_history) to see if it's still active. No luck? Go through the history a bit more and see if there's anything else in there.

5. Repeat until you find an active key, this can take a page or 20 of search results.

6. Found a key? Hot dog! Bundle that up in an email, fire it off to stripe and let the t-shirts roll in.

![](/img/20160523/email.png)

Know of any other places that offer swag for keys? Post a comment and let everyone know so we can cash in on it too.
