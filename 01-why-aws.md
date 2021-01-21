# Why is AWS important?

Before we can understand the basics of AWS, we need to know why AWS is important in the modern web development world. Let's take a look at how things worked __before__ AWS.

## A world without the cloud
Let's pretend we're in a world where AWS doesn't exist. We have a really cool website written in node and react that we want to publish to the web - a site that shows the world pictures of cats in sunglasses. What do we do?

First, we know the website consists of a _back end_ and a _front end_. Code for the backend typically runs on a single machine called a _server_. Code for the frontend is downloaded and run in the _browser_.
The first thing we need to do is put this code somewhere. So thousands of dollars later, we buy a really powerful computer, throw our code on that and start our node application in the terminal.
So our backend is running, great! But... how do other people access it? Well, this involves purchasing a domain (www.coolcats.com), then mapping the traffic that goes to that domain to direct towards our internal network.
Glossing over the details, we map www.coolcats.com to route to our server. However, as soon as we do this we start getting __a lot__ of traffic. Who knew so many people want to see cat pictures??
We need something to scan the traffic and ensure that we get the traffic we want and our poor server isn't overloaded. So we buy another expensive piece of machinery called a _load balancer_.
A load balancer is essentially a server whose only job is to redirect traffic or prevent traffic from overwhelming our application so it doesn't crash. With this, we're in business! But... we don't have a way for people to get our front end! What do we do?
Well, we need to ensure that our server can send the code for the front end to the browser so that it shows up. We add another route to our node application and redeploy. No big deal. But then we start getting complaints from people in the UK who __also__ want to see pictures of cool cats, 
but the images are loading really slowly since they are far away from our server. If only we could physically put another server in the UK! But that would be extremely expensive, and we are just a lowly developer trying to gift the world pictures of cool cats.

See how complicated and expensive this is getting? Luckily we don't live in a world like this and it is much easier to get up and running. Let's reevaluate this situation with AWS.

## A world with clouds
We have our back end and front end that we need to deploy on a server. Luckily AWS lets us buy space on their servers at a much cheaper price than buying our own hardware! 
We purchase a couple EC2 instances - or server spaces - and in our local terminal we can sign into the instances and begin running our code (note: this isn't how most companies do this, but we want to keep this to be a basic example). 
Now our code is running, we want a load balancer to distribute traffic to our various server, so we set up an Application Load Balancer to do that. We then route traffic to our server using Route53. 
We then serve our front end out of S3 rather than creating a route from our servers. We then can set up a Content Delivery Network (CDN) in AWS so people all over the world can see pictures of cool cats!

While a lot of those words likely don't mean anything to you, take my word that it is a lot easier and cheaper to use AWS rather than trying to do it yourself.
