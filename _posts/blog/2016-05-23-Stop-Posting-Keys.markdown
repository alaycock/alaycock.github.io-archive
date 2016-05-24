---
layout: post
title:  "How to get a free Stripe t-shirt, AKA stop exposing your API keys"
date:   2016-05-23 19:00:00
categories: blog
---

I'm probably preaching to the choir with this post, but it should be pretty obvious that if you ever commit one of your secret API keys to your git repository and push it, you should reset that key.

It doesn't matter how long it was exposed, or if you removed it in your next commit, or even if you modified your git history and force pushed it to Github, it still needs to be reset. There are [lots](https://rosspenman.com/api-key-exposure) [of](http://www.programmableweb.com/news/how-to-find-secret-api-keys-github/how-to/2015/12/20) [articles](http://www.programmableweb.com/news/why-exposed-api-keys-and-sensitive-data-are-growing-cause-concern/analysis/2015/01/05) about key exposure, and explaining how keys can be used to spin up AWS instances to harvest bitcoins. [Github even has an article on how to deal with exposed sensitive data](https://help.github.com/articles/remove-sensitive-data/).

![](/img/20160523/computer.jpg)

The other day I found a number of exposed Stripe API keys on Github. I reported them to Stripe, and I was offered a free Stripe t-shirt as a token of appreciation. I'm always one for swag and helping others resolve security issues, so here's how to find some exposed keys for yourself.

![](/img/20160523/shirt.jpg)

1. Find some example code that people might base their project off of, [here's an example from Stripe](https://github.com/stripe/monospace-rails/blob/master/config/initializers/stripe.rb). Snag that variable name, and search Github for that.

2. [16,000+ code search results](https://github.com/search?q=Stripe.api_key&type=Code&utf8=%E2%9C%93). The key probably isn't visible right in the results, so open up some of those repos and hit the 'history' button for the file.

3. Go through the [file's history](https://github.com/stripe/monospace-rails/commits/8d8c9ff56755a51a8d58adc76f0c6e3bff828979/config/initializers/stripe.rb) and see check if there are keys in there. Don't forget to trace a little bit through `.env` and other config files.

4. When you find a key, fire off a [curl request to an API endpoint](https://stripe.com/docs/api#balance_history) to see if it's still active. No luck? Go through the history a bit more and see if there's anything else in there.

5. Repeat until you find an active key, this can take a while, and will make you wonder if it's worth automating.

6. Found a key? Hot dog! Bundle that up in an email, fire it off to stripe and let the t-shirts roll in.

![](/img/20160523/email.png)

You could very easily automate this process using Github's API by pulling down the history of any files containing potential keys, and testing any keys that are found. I'm also curious if there any services who actively search Github for keys that have been accidentally exposed? That seems like the kind of thing AWS could use to prevent malicious server usage, but I've never heard of anything along those lines.
