# SDCTF 2022 OSINT

[**Part of the ship...** [76 solves]](https://github.com/drewd314/Nahamcon-CTF-2022-Keeeber-OSINT-Writeups/blob/main/Keeber.md#keeber-1)   

## Part of the ship...
Difficulty: **Easy**  
Authors: `Blarthogg`  
Points: **150**

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
