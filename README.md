# CTF-Reverse-Game

## Describtion 
My friend has developed a very interesting game, according to him, but I can't open it. Help me!
## Writeup

### Try to open this game
As we can see, we can't run exe file.

![изображение](https://github.com/user-attachments/assets/70fc2646-18bb-45c9-a6cc-2694b9bc8ffc)

Let's see how does it looks in 010 Editor

![изображение](https://github.com/user-attachments/assets/2cb2c287-50bf-4c9d-948b-dd3d81874b84)

We can see that the flag.txt file is there. It looks like ZIP File, let's check it out

![изображение](https://github.com/user-attachments/assets/6f378654-3b4e-4019-89a1-0a479141becb)

True, thats ZIP. Let's change header to PK and save as .zip

![изображение](https://github.com/user-attachments/assets/44589fde-5752-44e6-9a98-e8fae770a773)

Success 

![изображение](https://github.com/user-attachments/assets/7eb94d71-c707-4b9a-9afc-d3484adc670a)

One little problem that zip requires password, i'll use [fcrackzip](https://www.kali.org/tools/fcrackzip/) to brute this pass.
![изображение](https://github.com/user-attachments/assets/eee61fba-661f-485f-ae82-368a193343fb)

```
fcrackzip -b -D -p rockyou.txt -u Game.zip 

PASSWORD FOUND!!!!: pw == spiderman

```

Among the parameters, `-b` means brute-force attack and `-D -p` means dictionary attack with password file `rockyou.txt`.

After all we have this string 

![изображение](https://github.com/user-attachments/assets/f0594448-70d6-49ea-988b-8711f3fd92be)

Let's decode this 

![изображение](https://github.com/user-attachments/assets/ed2c8e57-a4cc-4fa8-8fc6-7cbc95597925)

### Answer 

**This is our flag: CODEBY{n#ll_byt3_b3_l1ke}**


