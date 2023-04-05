# discord-time-traveler-bug
"exploit" that lets you timeout someone in the past

# how to reproduce
step 1 

get a unix timestamp in the past

unfortunately discord only allows as low as 1522960000


step 2

convert it to isoString

```
const date = new Date(unixTimestamp * 1000);
const isoString = date.toISOString();
```


step 3

post to `https://discord.com/api/v9/guilds/guild id/members/user id`

with body `"{\"communication_disabled_until\":\"" + isoString + "\"}"`


step 4 

done

![image](https://user-images.githubusercontent.com/66729830/230198882-6d79774e-32f1-4ff4-8509-623e8bf99cf9.png)
