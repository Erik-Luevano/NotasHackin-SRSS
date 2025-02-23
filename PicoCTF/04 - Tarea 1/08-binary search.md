Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/20/challenge.zip)

`ssh -p 63227 ctf-player@atlas.picoctf.net`Using the password `6abf4a82`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!

Hints:
1.- Have you ever played hot or cold? Binary search is a bit like that.
2.- You have a very limited number of guesses. Try larger jumps between numbers!
3.- The program will randomly choose a new number each time you connect. You can always try again, but you should start your binary search over from the beginning - try around 500. Can you think of why?

### Solución
WebShell
```
erik616-picoctf@webshell:~$ ssh -p 58671 ctf-player@atlas.picoctf.net
The authenticity of host '[atlas.picoctf.net]:58671 ([18.217.83.136]:58671)' can't be established.
ED25519 key fingerprint is SHA256:M8hXanE8l/Yzfs8iuxNsuFL4vCzCKEIlM/3hpO13tfQ.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:15: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[atlas.picoctf.net]:58671' (ED25519) to the list of known hosts.
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 250
Lower! Try again.
Enter your guess: 125
Higher! Try again.
Enter your guess: 187
Higher! Try again.
Enter your guess: 218
Higher! Try again.
Enter your guess: 234
Higher! Try again.
Enter your guess: 242
Lower! Try again.
Enter your guess: 238
Higher! Try again.
Enter your guess: 240
Lower! Try again.
Enter your guess: 239
Congratulations! You guessed the correct number: 239
Here's your flag: picoCTF{g00d_gu355_bee04a2a}
Connection to atlas.picoctf.net closed.
erik616-picoctf@webshell:~$ 

```