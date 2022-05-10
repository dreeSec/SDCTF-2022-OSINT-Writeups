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

I could have used [GHunt](https://github.com/mxrch/GHunt) to get the exact email, but from the Turing Test challenge I assumed the email was in the same format as `jack.sdctf@gmail.com`. After sending `amy.sdctf@gmail.com` an email demanding the flag, we get a response giving it to us.

![41f867a2d21f2a3628ff968ec2f93ffa](https://user-images.githubusercontent.com/74334127/167705729-d12f196c-59f3-4e8b-8630-9a28f21cb555.png)

flag: `sdctf{0p3n_S0uRCE_1S_aMaz1NG}`
