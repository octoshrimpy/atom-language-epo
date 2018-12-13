Welcome to Epo, a human-friendly markup language designed specifically for making and solving cryptography puzzles and ARGs! Supported only within [Atom Text Editor](https://atom.io/) (at the moment). Please download [at the package's page](https://atom.io/packages/atom-language-epo) to use within Atom.

Below is an explanation of each element and how they work.

# Can be used anywhere
These can be used anywhere in the document, no holds barred.

### Line comment
*Two forward slashes with an optional space, and then either content, or one of the keywords below.*

Line comments help you keep track of what has and hasn't completed. Think of them as notes to self, or todo lists. When compiled, line comments will not show up at all. When making puzzles, you can use them to remind you of where you have bugs or hacks that need fixed.

```
// regular text like this
//TODO
//HACK
//BUG
//DONE
//NOPE
```

![alt-text](https://i.imgur.com/17RA1kj.png)

### Idea
*Exclamation mark followed by a space, and then content.*

An idea is designed to help you quickly jot down thoughts you may want to flesh out or work on later.

```
! idea!
```

![alt-text](https://i.imgur.com/NDh7b4e.png)

### Divider + Named divider
*At least three dashes, or three equal signs.*

*For a named divider, drop your name between two lines of dividers.*

Dividers are used to separate content visually. Maybe your puzzle came in two parts, and you need to remember which part goes to which section.

They will only work if the first line has no spaces before it. The first character in the middle line can be anything.

```
---
or
===

====
= this is a named divider
====
```

![alt-text](https://i.imgur.com/KXaonyg.png)

![alt-text](https://i.imgur.com/e7qM8yK.png)



### Anchor Reference
*A @ followed by the reference anchor name. Spaces in the name do not break it. Wrap it all with parentheses.*

You can reference specific anchor tags that exist throughout the document. These references will create a clickable link that will scroll the user to the proper anchor in the compiled document.

```
(@anchor 3)
```

![alt-text](https://i.imgur.com/Zq6JRDh.png)

### Note
*Left-pointing caret, followed by a space, and then content.*

Notes exist to be left through the document, sort of like helper sticky notes.

```
> this is a note
```

![alt-text](https://i.imgur.com/545LKtl.png)

### Multi-line note
*right-pointing caret, followed by content and any amount of newlines, closed by a left-pointing caret.*

A multi-line note is similar to the regular note, except it can be multiline.  

```
<
    this note is multiline.
    it will add wordbreak where you add them.
>
```

![alt-text](https://i.imgur.com/mTYEFxf.png)


---
# Thought wrappers

Thought wrappers are useful to keep information together in one spot.

### Snippet + Snippet resolution
*Name of snippet, followed by an open parentheses, with an optional number or key for deciphering the clue and comma. Content is placed after that. A closing parentheses, followed by a set of curly brackets with the solved content immediately afer.*

Snippets are used for keeping track of what was decoded, how it was decoded, and what the original text was. Name it whatever the main idea was for decoding it (caesar, vigenere, spectrogram), and then drop the original clue in the first section. The second section is for the solved section.

```
caesar( 3,
    SODBHU
){
    player
}
```

![alt-text](https://i.imgur.com/4RSbVQr.png)

### Puzzle + Solution
*Open square bracket, optional space, name or number, space, and then a pipe ( | ). This optional will become an anchor automatically if it exists. Puzzle content follows after that, closed by a square bracket. Open parentheses immediately afterwards start the solution. Solution content goes within, followed by a matching closing parentheses.*

Puzzles keep track of all your clues in one spot. You will be using a lot of these. They have an optional name that becomes an anchor tag automatically if present, and a solution that follows.

```
[ 1 |
    this is a puzzle
](
    this is a solution
)
```

### Released clue + Found solution
*content wrapped by three backticks.*

Within a puzzle or a solution, you can have text that stands out. This will help you keep track of what was the original clue, and what the entire solution is.

![alt-text](https://i.imgur.com/zXVrfaS.png)

---
# Can only be used within thought wrappers

## Step + Numbered step
*Star followed by a space, followed by content, or a number followed by a period and a space, and then content.*

Steps help you keep track of what you have tried. They can be numbered or otherwise, and they can be indented within each other, however when parsed, they will not be indented (for now).

```
* this is a regular step

1. steps can also use . - * in front of digits to
2- create numbered steps. they do not have to be
3* in any sort of order, and will be placed how they are written.
```

![alt-text](https://i.imgur.com/WgW5lap.png)

---
# Cannot be used within thought wrappers

### Title
*Caret followed by a space and then content.*

When denoting individual sections, you can use a title to visually tell them apart.

```
^ This is my title
```

![alt-text](https://i.imgur.com/nEfmUvk.png)

### Subtitle
*Double carets followed by a space and then content.*

Subtitles usually follow titles, as extra information.

```
^^ Subtitles usually follow titles
```

![alt-text](https://i.imgur.com/nEfmUvk.png)

---
# Modifiers and help

order:
1. anchor
2. header
3. CSS class

### CSS classes
*period followed by the class, immediately after the element's tag.*

You can add one CSS class to a handful of elements. Just add a `.classname` after the element tag.

```
!.danger foo

>.helpful bar

<.blue-3
    baz
>
```

![alt-text](https://i.imgur.com/2suu98n.png)

### Headers
*header text wrapped by parentheses, immediately after an element's tag.*

Notes and ideas can have headers as well. They are darker, bigger text, smaller than a title, that sit inside the parent element.

<!-- Colons and apostrophes are the only punctuation allowed within a header. -->

```
>(this is a header) notes can have short header.


!(hey listen:) ideas can have headers too!
```

![alt-text](https://i.imgur.com/x9GBSjs.png)

### Anchors
*Add an asterisk after an element's  tag.*

Anchors will drop an anchor tag in that specific element, for quickly navigating to it. They can be added to titles notes and ideas.

```
>#(anchors) notes can be anchor links as well.

<#(anchors 2) and here is the \n multiline version of it >

!#(anchors here) ideas as an anchor tag too

^# Titles can be anchors too, but the title is the main content.
^^ subtitles cannot be anchor tags but they can hold (@anchor) tags
```

![alt-text](https://i.imgur.com/4h1Kgp5.png)
---


# //TODO:

* refactor element descriptions with:
    * tag
    * modifiers available
    * description
    * example
    * visual example


* Add "failed" and "success" modifiers to steps and numbered steps, to keep track of what worked and what didn't.


* Create parser to convert epo files into clean html documents.
    * Add custom css to parser output.
<!--  -->
