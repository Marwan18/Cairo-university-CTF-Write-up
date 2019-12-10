# Cairo-university-CTF-Write-up

#### There were two easy web Challenges so let's see them

## Watch me
After opening the challenge it redirect us to an image [watch-me/mr-robot-safety-tips-featured.jpg](http://54.93.122.202/watch-me/mr-robot-safety-tips-featured.jpg)

![mr_robot2](https://user-images.githubusercontent.com/34393428/70561660-dc944d00-1b58-11ea-800f-514302125d3f.png)

So let's `intercept` the HTTP-Request using Burpsuite

![Screenshot 2019-12-10 13:06:08](https://user-images.githubusercontent.com/34393428/70561940-71974600-1b59-11ea-86a9-e9ee617069e4.png)

Umm , it's javaScript code to redirect us to this image so we want to beat it 
By changing the request method to `HEAD` it will just ask for Response Headers with out the body of the response

![flag](https://user-images.githubusercontent.com/34393428/70562656-d4d5a800-1b5a-11ea-8306-cac8e6b3c1ee.png)

And here is the flag Flag: `flag{3v0lv3_or_d13}`

---
## Information Thieves

let's run dirsearch 

![dir](https://user-images.githubusercontent.com/34393428/70563574-7a3d4b80-1b5c-11ea-8d20-cf591045b1d6.png)

And here we go 
let's download .git and see what we have 

![download](https://user-images.githubusercontent.com/34393428/70563927-2ed76d00-1b5d-11ea-8bec-f502bc9d6db9.png)
![fck](https://user-images.githubusercontent.com/34393428/70564144-9ab9d580-1b5d-11ea-9ed6-bf3d50a52d54.png)
We found `$secret_key = 'be607453caada6a05d00c0ea0057f733';` i have tried to submit the Secret Key but it was wrong 
so i used [hash analyzer](https://crackstation.net/) be607453caada6a05d00c0ea0057f733	md5(md5) ->	`lifeafterdeath` and it's the flag 

