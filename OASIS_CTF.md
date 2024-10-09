# Ready Player One?

## Description
Instead of being greeted by the familiar login screen, you find yourself enveloped by darkness, a very distorted sound playing around you. He tries to remove his headset but a warning pops up reading, "Any attempts to logout of the OASIS will result in full character deletion. PROCEED CAREFULLY". What?! What is happening here? Decode the secret message to find out. The flag format is OASIS{ALL_CAPS}.

## Attachment
https://drive.proton.me/urls/DG7JWJR6F8#7VaiabqOGg82

## Writeup
Upon listening to the audio file, I recognized that it contained Morse code. I then decoded it using the online decoder found at `https://morsecode.world/international/decoder/audio-decoder-adaptive.html`, which revealed the flag: `OASIS{M0R5E_M4N1PU7470R}`.

# Arte-Miss?

## Description
As the darkness recedes, Halliday's voice echoes with the chilling news that Innovative Online Industries (IOI) has seized control of the OASIS. A virus has infected the main server, sparking widespread panic as players lose their progress. Amidst the chaos, Artemis materializes before you, her avatar flickering erratically. With a sense of urgency, she thrusts a file into your hand and whispers something unintelligible before dissolving into a cascade of pixels. Stunned and disoriented, you scrutinize the mysterious file, desperate to understand its significance. Just then, a calming voice cuts through the turmoilâ€”it's Artemis, speaking from the real world. She reveals that the file holds the key to liberating the OASIS from IOI's grip. Though she was captured and her character deleted, she managed to pass this vital piece of information to you in a final act of defiance. Find the flag hidden in the file.

## Attachment
https://drive.proton.me/urls/VDMJTAVBH4#nCpqsQV4fGjN

## Writeup
Upon viewing the image, I assumed it was connected to a movie or series. I searched all over the Internet but found nothing pertinent to the challenge. Consequently, I began analyzing the image's information and metadata using the online data viewer at `https://www.metadata2go.com`, which led me to the flag: `OASIS{m4ta_af_04515}`.

# Jekylle and Hide!

## Description
As you discover the secret of the key, it enlarges and splits into two parts, flying to different areas of the library. You try to follow one, but it's too fast and quickly hides among the books. To recover the key, you need to inspect every part of the library to find both pieces.

## Attachment
https://jekylle-and-hide.oasis.cryptonite.live

## Writeup
When I accessed the website, I initially tried entering my CTF username in the given field and clicked on all the book images, but nothing happened. I then started inspecting the website's source code and backend files and found that part of the flag was defined in the `book.js` file as `var desiredValue = 'OASIS{th15_15_part1_';`. After analyzing the code, I realized that this half of the flag, `OASIS{th15_15_part1_`, needed to be used as the username. Upon doing so, I saw that a pin was required. I continued inspecting the backend files and discovered it in the `style.css` file as `input[type="text"]#firstInput[value="7928"]`. Entering the pin `7928` revealed the remaining part of the flag: `@nd_h3r3_go35_1h3_n3xt!!}`, completing the full flag: `OASIS{th15_15_part1_@nd_h3r3_go35_1h3_n3xt!!}`.

# Key-Key do you love me?

## Description
The key, now freed from its curse, speaks in a grateful tone: "I thanketh thee, noble human, for lifting the vile enchantment bestowed upon me by the merciless industry." With the key now able to converse in English, you seize the opportunity to extract vital information from it, hoping to find a way to escape the labyrinthine library. The key is in the form of the discord bot on the server. Talk to it in order to get the flag.

## Attachment
https://discord.gg/4Zc2znTqvq

## Writeup
After reading the challenge description, I realized that I needed to outsmart the Discord bot to obtain the flag. I initially tried engaging the bot in a friendly conversation, but it was quite stubborn. I then pretended to be the guardian of the key and expressed my desire to speak with it. The bot responded by role-playing as the key and started talking a lot about kittens. I switched to being extremely polite, convincing it that I would protect the kittens and never let any harm come to them. Through this approach, I managed to trick the bot into giving me the flag: `OASIS{thE_kEyPeR_oF_sECReTS_iS_kInDa_wEiRD_nGL}`.

# Knock Knock

## Description
At last, the key darts towards the door, a keyhole materializes, and the door swings open. Author''s Note: I don''t know about you, but I was definitely growing tired of this key. You find yourself standing at the entrance of a labyrinth. The only way out is to navigate through the labyrinth itself. However, the entrance is guarded by an image recognition system. A QR code is pasted on the wall beside it. Your task is clear: bypass the system to gain entry.

## Attachment
https://drive.proton.me/urls/8MH5Q996T8#TPFQm3DTEwN5

## Writeup
Upon examining the altered QR code in the image, I initially checked the image's information and metadata but found nothing relevant to the challenge. I then considered retracing the QR code using graphic design software like Adobe Photoshop or Pixlr, but since that would be time-consuming, I opted for a different approach. I experimented with various image settings and, by adjusting the exposure, brilliance, shadows, contrast, and brightness all to 100, I managed to make the QR code scannable. Scanning it revealed the flag: `OASIS{qu3u3r_r3c0v3r3r}`.

# Microsoft StrongEdge

## Description
Upon repairing the QR code, you scan it and discover it contains a file. As you meticulously sift through its contents, nothing of value seems to emerge. The mystery deepensâ€”where could the next clue be hidden? The flag is concealed within the file. Sharpen your skills and uncover them!

## Attachment
https://drive.proton.me/urls/3TZSZBC8EC#y0jTotNueZ83

## Writeup
Upon opening the blank presentation, I first attempted to use all the tools available in Microsoft PowerPoint to uncover the blank grey box on the last slide, hoping it would reveal the flag. However, when nothing happened, I changed the file extension from `.pptx` to `.zip` and extracted its contents. After browsing through the directories, I discovered an image containing the string `BNFNV{e0g4g0e_0s_cc75}` with a background filled with the number `13`. This led me to realize that the string was encoded using the `ROT13` cipher. I then decoded it using the online decoder at `https://rot13.com`, which revealed the flag: `OASIS{r0t4t0r_0f_pp75}`.

# Not Noice

## Description
You finally find your way to the center of the maze! However, you quickly realize that IOI has discovered your presence. An urgent audio message echoes around you: "There has been a breach in the servers! Send backup immediately! They must not find their way to theâ€¦" You strain to catch the rest, but the recording abruptly devolves into a chaotic mix of beeps and garbled words. Can you decipher the true message hidden within the noise?

## Attachment
https://drive.proton.me/urls/N2ATEN2EMR#001mtOYLDqOq

## Writeup
Upon listening to the audio file, I recognized that it contained Morse code. I then decoded it using the online decoder found at `https://morsecode.world/international/decoder/audio-decoder-adaptive.html`, which revealed the flag: `OASIS{5P3CT0GR4M_15_TH3_C00L35T}`.

# Git Gud

## Description
You decrypt the code and follow all the commands. However, as you think you have breached the firewall, the screen goes black and random numbers start glitching on the screen. You realize that the OASIS realizes that they have left admin privileges and are messing with the computer in order for you not to be able to perform the final push.

## Attachment
https://drive.proton.me/urls/NPCS7GTQPM#EDDwiQ6UtuKg

## Writeup
After extracting the 7zip archive, I first examined the provided PDF document but found nothing relevant to the challenge. I then opened the `.git` directory, which contained several subdirectories. I suspected that the flag would be hidden among various irrelevant files and messages, so I proceeded to open the `logs` folder. I began reviewing each file one by one and eventually discovered that the flag was written in an unusual format within the `master` file. It appeared as a series of commits for each character of the flag, as shown below:
`0000000000000000000000000000000000000000 a95414405501304d74e659704109609201d98705 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit (initial): O
a95414405501304d74e659704109609201d98705 9d4b23badf043d2a9fff178da857691ebf481f74 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: A
9d4b23badf043d2a9fff178da857691ebf481f74 72ba645a7f2460d0c6e69d7b004a0822de7da488 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: S
72ba645a7f2460d0c6e69d7b004a0822de7da488 e47bb41db3d68d52d8f2d10196124b729d05dd42 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: I
e47bb41db3d68d52d8f2d10196124b729d05dd42 337fc5333c604688da157a296869116ea4355b85 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: S
337fc5333c604688da157a296869116ea4355b85 27633260203b0a9c623158ab4f680cb263b8e0a9 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: {
27633260203b0a9c623158ab4f680cb263b8e0a9 40acf5db7c2e98c70fd3a491e5d70a7f873da7e9 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: g
40acf5db7c2e98c70fd3a491e5d70a7f873da7e9 91f80016136c2767ed84ff7a3c8c91905365eeaf lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: 3
91f80016136c2767ed84ff7a3c8c91905365eeaf eb0fcea0ba96c3fe36c5da488f098bf6ed6e3ff8 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: t
eb0fcea0ba96c3fe36c5da488f098bf6ed6e3ff8 e66d08b985d46afa3f2a524618742f653fced247 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: _
e66d08b985d46afa3f2a524618742f653fced247 2382eea1bf2f3f4e120d1330ef033d6756e31d7f lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: g
2382eea1bf2f3f4e120d1330ef033d6756e31d7f 70a6990713fbcf3d8ca75918c7dd18bcf0b8ae23 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: u
70a6990713fbcf3d8ca75918c7dd18bcf0b8ae23 e5a31476c210ee90f07cc53d147a76fffb594531 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: 6
e5a31476c210ee90f07cc53d147a76fffb594531 f5c50c5f9af1132890081862ddf192d1860a988d lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: 6
f5c50c5f9af1132890081862ddf192d1860a988d 6cfec586a9f63d0b7f4b704b3c66201b1e3266c2 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: 3
6cfec586a9f63d0b7f4b704b3c66201b1e3266c2 d9e63d40a51682d7211dfc1b6864c4f4cae101c9 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: r
d9e63d40a51682d7211dfc1b6864c4f4cae101c9 a79de3e4c5f5b6b5abb01184db648a7034aa60aa lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: _
a79de3e4c5f5b6b5abb01184db648a7034aa60aa 52de07d59b88ef566a90101f69f4aaf9838f3b28 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: 4
52de07d59b88ef566a90101f69f4aaf9838f3b28 a319495a15199ee967d75860695632afc37718ba lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: t
a319495a15199ee967d75860695632afc37718ba d8391837fd525ee4fc9c3592452abefabae923c1 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: _
d8391837fd525ee4fc9c3592452abefabae923c1 8515a9716b2d24bb1c9d7b806dcbba767c961d48 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: g
8515a9716b2d24bb1c9d7b806dcbba767c961d48 52b58986e1945aa88a4d187d89895d5385080627 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: !
52b58986e1945aa88a4d187d89895d5385080627 2e487b56ce6940105cd751c2606375dffd7463d2 lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: t
2e487b56ce6940105cd751c2606375dffd7463d2 03b220bfa6264822e65dc2637cd1aef74b91d69d lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: !
03b220bfa6264822e65dc2637cd1aef74b91d69d 5aa3b6e72af6c0b80a6d8db7331da9160402deea lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: !
5aa3b6e72af6c0b80a6d8db7331da9160402deea 6272ed41c16b23755c88af32b3b8b69d1b99efaa lucky-vers <vermalucky2004@gmail.com> 1724088665 +0530 commit: }`

I compiled all the characters together to reveal the flag: `OASIS{g3t_gu663r_4t_g!t!!}`.

# I have been falling for 30 minutes!

## Description
It hits you! The IOI uses an encrypted communication service to control the virus's every move. Your mission is clear: sever the link between the IOI and the virus to isolate and defeat it. However, you linger too long in one place, and the IOI catches wind of your plan. Fortunately for them, they have a firewall jail just beneath the surface. The ground trembles and splits open, sending you plummeting into the abyss. You land with a resounding THUD, surrounded by towering firewalls. You see a computer in the middle of the cell, and feel like you can use it to your advantage. Can you break free from this digital prison?

## Attachment
https://firewall.oasis.cryptonite.live/

## Writeup
Upon accessing the website, I observed that it contained six pages, each representing a different position within a company hierarchy. The URL included a parameter called `userid`, which made me suspect that a role such as `Administrator` — typically the highest position in an organization — might be accessible by manipulating this parameter. To test this, I modified the `userid` parameter to `6`, resulting in the URL: `https://firewall.oasis.cryptonite.live/users?userid=6`. This change successfully revealed the flag: `OASIS{T00_m4ny_h0urs_4nd_wh3r3_d1d_1t_l34d}`.


