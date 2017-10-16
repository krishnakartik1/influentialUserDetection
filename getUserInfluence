import twitter
from twitter import TwitterError
api=twitter.Api(consumer_key='iLycHH4YP0JOMXQbNycbkBRqh',
                consumer_secret='8S00MTSvi9RiwRVLpajk1V9y2e9ZSiNNt6gD1UCMsJCWcSrz2c',
                access_token_key='3383560760-uBUnPzyuiu4Or7klpHzHf6TfKwY2SqZvjxooB7I',
                access_token_secret='Ii6wA6dA24Pb06xibXyhRb8e2trf5bg2w6JDkrWpjVL2A')
f=open("twitteridsnew.txt","r")
ct=0
f2=open("twitterInfluence.txt","a")
twitterIds=f.read().split(" ")
for one in twitterIds:
    user = api.GetUser(user_id=int(one))
    tweetCount = 0
    statuses = api.GetUserTimeline(user_id=int(one))
    ownTweets = []
    influence = 0
    for tweet in statuses:
        print("Tweet")
        if tweet.text[0]!="R" and tweet.text[1]!="t":
            tweetCount = tweetCount + 1

            print(tweet)
            ownTweets.append(tweet)
            print("\n")
    if tweetCount == 0:
        followers = user.followers_count
        influence = followers
    else:
        for tweet in ownTweets:
            try:
                retweeters = api.GetRetweeters(tweet.id)
            except TwitterError as e:
                print(e)
                continue
            for each in retweeters:
                try:
                    followers = api.GetFollowerIDs(user_id=each)
                except TwitterError as e:
                    print(e)
                    continue
                influence = influence + len(followers)
        influence = influence + user.followers_count
    if tweetCount!=0:
        print(user.screen_name+" "+str(influence)+"*")
        f2.write(user.screen_name+" "+str(influence)+"*"+"\n")
    else:
        print(user.screen_name+" "+str(influence))
        f2.write(user.screen_name+" "+str(influence)+"\n")
    print("ct:"+str(ct))
    if ct>=100:
        exit(0)
    ct=ct+1




