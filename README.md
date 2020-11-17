# Twitter_BOT
:-i'm hoping that you have some basic-sence nothing else!

#### Twitter BOT from Scratch to Deployment :)

first you will need a twitter developer account! so go to [Twitter Developr](https://developer.twitter.com/en)

after making a developer account (if you are facing issuse than i cant do anything:() 

NOTE:-Consumer keys are the API KEYS too

copy paste all the the given keys into your notepad!

--Coding Part--
now you have to install "Tweepy" python lib that will help you to make contact with you twitter develpoer account!

1 .make a folder named BOT

2.type following command in terminal

`git init`


`pip install Tweepy`

3.make a python file named= bot.py


after this authantication comes into the role just copy paste keys from your notepad into the python file


```
import Tweepy

CONSUMER_KEY = "--"

CONSUMER_SECRET = "--"

ACCESS_KEY = "--"

ACCESS_SECRET = "--"

auth = tweepy.OAuthHandler(CONSUMER_KEY, CONSUMER_SECRET)
auth.set_access_token(ACCESS_KEY, ACCESS_SECRET)

api = tweepy.API(auth)
```

after this you will write functions that will like and retweet

```
QUERY='#programming' or '#technology' or '#coding' // you can edit this 
LIKE= True
FOLLOW= True
  
for tweet in tweepy.Cursor(api.search, q = QUERY).items(): 
        try: 
            print('\nTweet by: @' + tweet.user.screen_name) 
            tweet.retweet() 
            print('Retweeted the tweet') 
    
            if LIKE: 
                tweet.favorite() 
                print('Favorited the tweet') 

            if FOLLOW: 
                if not tweet.user.following: 
                    tweet.user.follow() 
                    print('Followed the user') 

            sleep(300)
        except tweepy.TweepError as e: 
                print(e.reason)

        except StopIteration: 
              break
 ```
 
your final python file will look like {if it is not same as yours so make it same}:-

```
import tweepy
from time import sleep


CONSUMER_KEY = "--"
CONSUMER_SECRET = "--"
ACCESS_KEY = "--"
ACCESS_SECRET = "--"
auth = tweepy.OAuthHandler(CONSUMER_KEY, CONSUMER_SECRET)
auth.set_access_token(ACCESS_KEY, ACCESS_SECRET)

api = tweepy.API(auth)

QUERY='#programming' or '#technology' or '#coding'
LIKE= True
FOLLOW= True
  
for tweet in tweepy.Cursor(api.search, q = QUERY).items(): 
        try: 
            print('\nTweet by: @' + tweet.user.screen_name) 
            tweet.retweet() 
            print('Retweeted the tweet') 
    
            if LIKE: 
                tweet.favorite() 
                print('Favorited the tweet') 

            if FOLLOW: 
                if not tweet.user.following: 
                    tweet.user.follow() 
                    print('Followed the user') 

            sleep(300)
        except tweepy.TweepError as e: 
                print(e.reason)

        except StopIteration: 
              break
 ```

if you try to run this file in terminal via `python filename.py`

you will see your output if not then its your mistake please copy paste carefully!

in terminal :-`git add .`


               `git commit -m 'bot file created'`

# Deployment

we will deploy our python file on Heroku!

go to Heroku official website and make your FREE account after this in you folder make a file named "Procfile" (P capital)
and type following

`worker : python bot.py`

save this!

Go [Here!](https://blog.heroku.com/the_heroku_toolbelt) and download it in your machine!

in terminal type `heroku login` 

after successfully login in terminal

type


`heroku git:remote -a your_app_name_here`


`git push heroku master`

and you have to on the app manually!
and your twitter BOT is READY!

Being Updated With time
