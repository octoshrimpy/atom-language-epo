Welcome to Epo, a human-friendly markup language designed specifically for making and solving cryptography puzzles and ARGs!

# can be used anywhere
These can be used anywhere in the document, no holds barred.

### Line comment
*Two forward slashes with an optional space, and then either content, or one of the keywords below.*

Line comments help you keep track of what has and hasn't completed. Think of them as notes to self, or todo lists. When compiled, line comments will not show up at all. When making puzzles, you can use them to remind you of where you have bugs or hacks that need fixed.


* // regular text like this
* //TODO
* //HACK
* //BUG
* //DONE
* //NOPE

![alt-text](https://i.imgur.com/17RA1kj.png)

### Idea
*Exclamation mark followed by a space, and then content.*

An idea is designed to help you quickly jot down thoughts you may want to flesh out or work on later.

* ! idea!

![alt-text](https://i.imgur.com/NDh7b4e.png)

### Divider + Named divider
*At least three dashes, or three equal signs.*

*For a named divider, drop your name between two lines of dividers.*

Dividers are used to separate content visually. Maybe your puzzle came in two parts, and you need to remember which part goes to which section.

They will only work if the first line has no spaces before it. The first character in the middle line can be anything.

* \---
* ===

![alt-text](https://i.imgur.com/KXaonyg.png)

![alt-text](https://i.imgur.com/e7qM8yK.png)



### Anchor Reference
*A @ followed by the reference anchor name. Spaces in the name do not break it. Wrap it all with parentheses.*

You can reference specific anchor tags that exist throughout the document. These references will create a clickable link that will scroll the user to the proper anchor in the compiled document.

* (@anchor 3)

![alt-text](https://i.imgur.com/Zq6JRDh.png)

### Note
*Left-pointing caret, followed by a space, and then content.*

Notes exist to be left through the document, sort of like helper sticky notes.

* \> this is a note

![alt-text](https://i.imgur.com/545LKtl.png)

### Multi-line note
*right-pointing caret, followed by content and any amount of newlines, closed by a left-pointing caret.*

A multi-line note is similar to the regular note, except it can be multiline.  

* < this is a multi-line note. >

![alt-text](https://i.imgur.com/mTYEFxf.png)


---
# Thought wrappers

Thought wrappers are used to keep information together in one spot.

### Snippet + Snippet resolution
*Name of snippet, followed by an open parentheses, with an optional number or key for deciphering the clue and comma. Content is placed after that. A closing parentheses, followed by a set of curly brackets with the solved content immediately afer.*

Snippets are used for keeping track of what was decoded, how it was decoded, and what the original text was. Name it whatever the main idea was for decoding it (caesar, vigenere, spectrogram), and then drop the original clue in the first section. The second section is for the solved section.

![alt-text](https://i.imgur.com/4RSbVQr.png)

### puzzle + solution
### released clue + found solution

---
# can only be used within thought wrappers

## step + numbered step

---
# cannot be used within thought wrappers

### title
### subtitle

---
# modifiers and help




<!--  -->
