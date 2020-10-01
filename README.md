# YouTube Video Lister

A python app which searches predefined query on YouTube using YT Data API and saves it in MongoDB and lists it on dashboard.

It searches asynchronously in background using Python asyncio and threading library.

## Asyncio Library

The asyncio module provides a framework that revolves around the event loop.It is designed to use coroutines and futures to simplify asynchronous code and make it almost as synchronous code as there are no callbacks.

## Threading Library

Threading in python is used to run multiple threads (tasks, function calls) at the same time.

Predefined search query: "game"

Time Interval for searching: 60sec

### Live: [Mini YT LOL](https://mini-yt-lol.herokuapp.com/dashboard) - Hosted on Heroku

## Starting Server Locally
```bash
git clone https://github.com/abhishekraj272/youtube-video-lister.git

cd youtube-video-lister

pip3 install -r requirements.txt

# Set Env Var: MONGODB_URI, TotalAPISet, YTAPIKey1, YTAPIKey2, YTAPIKey3....
# TotalAPISet = count(  YTAPIKey1, YTAPIKey2, YTAPIKey3.... ) 

flask run 
# OR
gunicorn run:app
```
## Heroku

Heroku is a platform as a service (PaaS) that enables developers to build, run, and operate applications entirely in the cloud.

## Deploying on Heroku

```bash
heroku login

heroku create

heroku config:set MONGODB_URI=<MONGODB_URI>
heroku config:set TotalAPISet=<TotalAPISet>
heroku config:set YTAPIKey1=<YTAPIKey1>
.
.
.

git push heroku master

heroku open
```

## Features
1. Shuffles through the provided API Key set every time it searches.
2. View function is cached for 60sec for every args provided.
3. Sort & Filter Options are provided.
4. The data fetched from YT are latest.

## Tools - Used:
1.Flask (It is a micro web framework written in python) 
2.Pymongo (It is a python distribution containing tools for working with the MongoDB, and is the recommended way to work with MongoDB from python) 
3.Flask Caching (It is an extension to Flask that adds caching support for various backends to any Flask application)

Note: [Mini YT LOL](https://mini-yt-lol.herokuapp.com/dashboard) is running on a Free Tier MongoDB and Heroku server.
