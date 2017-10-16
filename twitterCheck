import twitter
api=twitter.Api(consumer_key='iLycHH4YP0JOMXQbNycbkBRqh',
                consumer_secret='8S00MTSvi9RiwRVLpajk1V9y2e9ZSiNNt6gD1UCMsJCWcSrz2c',
                access_token_key='3383560760-uBUnPzyuiu4Or7klpHzHf6TfKwY2SqZvjxooB7I',
                access_token_secret='Ii6wA6dA24Pb06xibXyhRb8e2trf5bg2w6JDkrWpjVL2A')
print(api.VerifyCredentials())
statuses=api.GetUserTimeline(screen_name='duttsanjay')
print(api.GetUser(screen_name='duttsanjay'))
globalRetweeterIds=[]
for tweet in statuses:
    print(tweet.text)
    retweetersIds=api.GetRetweeters(tweet.id,count=100)
    for each in retweetersIds:
        globalRetweeterIds.append(each)
    print(retweetersIds)
    print("\n")
import simplejson
filename="twitteridsnew.txt"
file=open(filename,'a')
for each in globalRetweeterIds:
    file.write(str(each)+" ")
print(globalRetweeterIds)