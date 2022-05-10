# SDCTF 2022 OSINT  
Team: **WolvSec**  

[**Part of the ship...** [76 solves]](https://github.com/drewd314/Nahamcon-CTF-2022-Keeeber-OSINT-Writeups/blob/main/Keeber.md#keeber-1)   
[**Google Ransom** [155 solves]](https://github.com/drewd314/Nahamcon-CTF-2022-Keeeber-OSINT-Writeups/blob/main/Keeber.md#keeber-1)  

## Part of the ship...
Difficulty: **Easy**  
Authors: `Blarthogg`  
Points: **150**
Solves: **76**

Challenge Description:  
Sometimes I worry about my friend... he's way too into memes, he's always smiling, and he's always spouting nonsense about some "forbidden app." I don't know what he's talking about, but maybe you can help me figure it out! All I know is a username he used way back in the day. Good luck! Flag format is sdctf{flag}  
**Username**  
DanFlashes

### Approach

I started off this challenge by looking up the username `DanFlashes` on different social media platforms to see if one was linked to SDCTF. I found one on Instagram, but it seemed unrelated to the competition. I went back to the prompt to see what other clues could lead us to this account. I decided to google “forbidden app” and found [urban dictionary definitions](https://www.urbandictionary.com/define.php?term=The%20Forbidden%20App) that this app is iFunny, and the definitions also mentioned being “part of the ship” (like the challenge name) so I figured this was the right social media.

![7fadfe7fa082d91833ab361ef2838bc3](https://user-images.githubusercontent.com/74334127/167702222-19189dbc-e0a9-4516-8847-adca688eb942.png)

Looking at DanFlashes [on iFunny](https://ifunny.co/user/DanFlashes), we see that this page does not exist. However, the challenge description states that this was “‘way back’ in the day” which hints that we should use the [Wayback Machine](https://web.archive.org/web/20220128003432/https://ifunny.co/user/DanFlashes) (always look for hints like these in OSINT challenges!). From this we can see a snapshot was taken January 28th of this year, which gives us the flag on DanFlashes' profile.

![ef2abb19a3e863ed42113d718faee08b](https://user-images.githubusercontent.com/74334127/167702201-ce5add5b-88cc-4ec3-9f4d-e0286f6b0155.png)


flag: `sdctf{morning_noon_and_night_I_meme}`

## Google Ransom
Difficulty: **Easy**  
Authors: `KNOXDEV`  
Points: **100**
Solves: **155**

Challenge Description:  
Oh no! A hacker has stolen a flag from us and is holding it ransom. Can you help us figure out who created this document? Find their email address and demand they return the flag!
**Attachments**  
[ransom letter](https://docs.google.com/document/d/1MbY-aT4WY6jcfTugUEpLTjPQyIL9pnZgX_jP8d8G2Uo/edit)  

### Approach  
From the ransom letter, we see a cryptic note about someone threatening to sign their email up for an annoying newsletter. As threatening as this is, it doesn’t give us any information about who made this google doc. However, since it’s google there is likely a way to view the email of this account owner. I went to the “shared with me” section on google drive to get more information about the random letter. Looking at `Details`, we can see that the owner of the document is `Amy SDCTF`. 

![93b795b318ec39dc1b60e22e0e9b1c93](https://user-images.githubusercontent.com/74334127/167705712-72ada725-3691-4980-b6fd-69dbf17ac075.png)

I could have used [GHunt](https://github.com/mxrch/GHunt) to get the exact email, but from the Turing Test challenge I assumed the email was in the same format as `jack.sdctf@gmail.com` and confirmed this on [epieos](https://epieos.com/). After sending `amy.sdctf@gmail.com` an email demanding the flag, we get a response giving it to us.

![41f867a2d21f2a3628ff968ec2f93ffa](https://user-images.githubusercontent.com/74334127/167705729-d12f196c-59f3-4e8b-8630-9a28f21cb555.png)

flag: `sdctf{0p3n_S0uRCE_1S_aMaz1NG}`

## Samuel
Difficulty: **Medium**  
Authors: `k3v1n`  
Points: **88**
Solves: **160**

Challenge Description:  
Where is this?
https://www.youtube.com/watch?v=fDGVF1fK1cA

Flag format: sdctf{latitude,longitude} using decimal degrees and 3 decimal places rounded toward zero (Ex. 4.1239 → 4.123, -4.0009 → -4.000)

Example: If the location were https://goo.gl/maps/TnhzfxXKg9TDYDfR9 the flag would be sdctf{38.889,-77.035}  
**Note**  
The youtube channel/account is not relevant to this challenge. Only the video content is relevant.

### Approach  
The video linked shows us a blinking beacon at night, with a plane flying by in the distance. I initially thought this was an [Aviation OSINT](https://www.osintessentials.com/aviation) since the plane in the background was the only other thing in the video. I had no idea how to use the beacon or distant plane.

As the competition progressed, I saw that the challenge had a lot of solves and I figured it likely wasn’t some insanely hard Aviation OSINT. I then realized the blinking beacon was likely morse code. `.-- .... .- - / .... .- - .... / --. --- -.. / .-- .-. --- ..- --. .... -` translated to **WHAT HATH GOD WROUGHT**. After googling what that means, we learn it was [the official first Morse code message transmitted in the US](https://en.wikipedia.org/wiki/What_hath_God_wrought#:~:text=%22What%20hath%20God%20wrought%22%20is,the%20Baltimore%E2%80%93Washington%20telegraph%20line).

I thought then the location may be where the message was originally transferred or received, but couldn’t find anything there. I then just searched “What hath god wrought” on Google Maps and found a sculpture at the University of California San Diego. Seeing that the competition is hosted by San Diego State University, I assumed this was the right spot. From this we can get the coordinates on [Google Maps](https://www.google.com/maps/place/What+Hath+God+Wrought/@32.8751745,-117.2408527,21z/data=!4m5!3m4!1s0x80dc07e0d30e81a7:0x69087278617d6b1d!8m2!3d32.8752134!4d-117.2407749) in the url, and truncating 32.8751745,-117.2408527 to get the flag..

![79a5590b9250425ef5d4ed03405ba657](https://user-images.githubusercontent.com/74334127/167709182-cbae98ae-76ed-4d13-adad-22767cca5c78.png)

flag: `sdctf{32.875,-117.240}`

## Turing Test
Difficulty: **Medium**  
Authors: `Blarthogg, KNOXDEV`  
Points: **49**
Solves: **200**

Challenge Description:  
My friend has been locked out of his account! Can you help him recover it?  
**Email**  
jack.sdctf@gmail.com  
**Website**  
https://vault.sdc.tf/  
**Note**  
Twitter does not need to be used for this challenge.

### Approach  
My first step in this challenge was going to the website, and started spamming random passwords to see what would happen. After 5 incorrect guesses, an `Account Support` window is prompted. We are then asked security questions to get back into our account (as well as bread puns).

![a78305e4a4cdec015b7de26dda34d0db](https://user-images.githubusercontent.com/74334127/167715998-a643e9f5-04c0-4e82-994f-9584db96c296.png)

For the first prompt, we are asked our name. We can use [epieos](https://epieos.com/) on Jack’s email to find his name is Jack Banner.

![7c8f47781693d3d5c2decfb0ea295254](https://user-images.githubusercontent.com/74334127/167716017-b7624b46-47e1-47d8-8db4-534ca35f1844.png)

Next we are prompted with “What month were you born in?” I wasn't sure if you were supposed to brute force this but figured since it was an OSINT challenge thre would be a social media account. Epieos showed Jack’s email as being connected to a Twitter, but luckily the challenge admin noticed this as well and added a disclaimer that twitter does not need to be used. What could have happened is someone else registered an account with that email, which admins have to be prepared to fix for these kinds of challenges. I tried other social media platforms, and specifically ones that I did not explore yet. OSINT categories usually try to avoid using the same platform twice. Looking up “Jack Banner” on Facebook, we see [the account](https://www.facebook.com/profile.php?id=100077609021228) we are looking for.

![81adfedda8cb78d2a9b906fe1116eca0](https://user-images.githubusercontent.com/74334127/167716070-f7164142-add5-4099-ac4c-b1a03027aab6.png)

The first post we can use to find his birthday by a quick google search of “99 days before april 19” giving us their birthday of January 10th.

![780281d7da8fd1e78da0918bc65873ab](https://user-images.githubusercontent.com/74334127/167716380-ef9df5e8-1f32-41fc-ac59-0e9af1005574.png)

The next prompt is “What is the name of your dog?” Looking around more on their facebook, we see an instagram for their dog linked in the Intro section. Something I learned from this challenge is that this can **only be seen if you are logged into Facebook**, so for some OSINT challenges you may need to be logged in. Although for regular OSINT gathering usually you don’t want to alert the person you are looking at, such as on LinkedIn. On the Instagram account we see that the dog’s name is Ravioli.

![6f122865ff944bf3b96112ede45e5c2c](https://user-images.githubusercontent.com/74334127/167716403-a13e50ce-0cc7-40ca-88aa-91f8d353cdc0.png)
![eefea3f0e97d1ebac12733186ddca7f2](https://user-images.githubusercontent.com/74334127/167716417-e39e1b65-d345-44a1-87b3-035ced79635f.png)

The final prompt is “What are the first six characters of your flag?” which is `sdctf{` for this CTF. This lets us access the flag vault and get the flag.

![986f972701471294de5c5baf8d7e308f](https://user-images.githubusercontent.com/74334127/167716436-39497d60-00e9-42ae-adc9-62f7a1572d07.png)

flag: `sdctf{7he_1m1747i0n_94m3}`

