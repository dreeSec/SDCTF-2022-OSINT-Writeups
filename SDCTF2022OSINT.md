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

I thought then the location may be where the message was originally transferred or received, but couldn’t find anything there. I then just searched “What hath god wrought” on google maps and found a sculpture at the University of California San Diego. Seeing that the competition is hosted by San Diego State University, I assumed this was the right spot. From this we can get the coordinates on [google maps](https://www.google.com/maps/place/What+Hath+God+Wrought/@32.8751745,-117.2408527,21z/data=!4m5!3m4!1s0x80dc07e0d30e81a7:0x69087278617d6b1d!8m2!3d32.8752134!4d-117.2407749) in the url, and truncating 32.8751745,-117.2408527 to get the flag..

![79a5590b9250425ef5d4ed03405ba657](https://user-images.githubusercontent.com/74334127/167709182-cbae98ae-76ed-4d13-adad-22767cca5c78.png)

flag: `sdctf{32.875,-117.240}`



