![[Pasted image 20230425002429.png]]

To create a regex pattern that matches the text structure you provided, where the front of the flashcard is on one line and the back of the flashcard is on the next line, you can use the following regex pattern:

```
^(.+)\n\n(.+)
```

Here's a breakdown of the regex pattern:

- `^`: matches the beginning of a line.
- `(.+)`: captures one or more characters (the `+` quantifier). The first group represents the front of the flashcard.
- `\n\n`: matches two newline characters, representing the blank line between the front and back of the flashcard.
- `(.+)`: captures one or more characters (the `+` quantifier). The second group represents the back of the flashcard.

Please note that this regex pattern assumes that there is always a blank line between the front and back of the flashcards. If the structure of your text changes, you may need to adjust the pattern accordingly.

> I test the regex
> ![[Pasted image 20230425000744.png]]![[Pasted image 20230425000744.png]]


![[Pasted image 20230425002358.png]]

>I test again, It still works!
>![[Pasted image 20230425002206.png]]
>I build my obsidian to anki work stream sucessfully!
>![[Pasted image 20230425002640.png]]
>![[Pasted image 20230425011549.png]]