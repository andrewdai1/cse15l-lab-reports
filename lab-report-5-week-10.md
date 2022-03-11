# Lab Report 5 Week 10
## Andrew Dai A16366706
---
**Finding Tests**

I simply manually looked through the test files and looked for 
specifically interesting test files that may produce strange or at 
least different results. 

From manual searching, I found that test 201 and 489 had interesting
and different results for both implementations of markdown parse.

---

**Test 201**

Test 201 looked like this:
```
[foo]: <bar>(baz)

[foo]
```

The expected output should just be nothing, as this is not a valid
markdown link as there is stuff between the brackets and parentheses.

My implementation output:
```
[]
```

Provided implementation output:
```
[baz]
```

In this case, my implementation was correct, as it correctly saw that
there was not valid link and gave nothing. However, the provided
implementation had a bug, where it mistakenly listed a link. The bug 
was that the implementation did not check for any characters between 
the closed bracket and open bracket, as any character between the
closed bracket and open bracket makes it not a valid markdown link.

In lines 63 and 64 of the provided implementation:
```
int nextCloseBracket = markdown.indexOf("]", nextOpenBracket);
int openParen = markdown.indexOf("(", nextCloseBracket);
```
Here in between these lines, should be a check whether the next open
parentheses is right next to the closed bracket.

---
**Test 489**

Test 489 looks like this:
```
[link](foo
bar)
```
This is not a valid link, as there is an extra \n inside the 
parentheses. So the expected output should also be nothing.

My implementation output:
```
[foo
bar]
```
Provided implementation output:
```
[]
```

In this case, my implementation had the incorrect output. The bug was 
that it did not check for a new line character when parsing the links,
and mistakenly think that the markdown file has a link if it had a 
new line character in between the parentheses.

In lines 36-42 of my implementation:
```
int openParen = markdown.indexOf("(", nextCloseBracket);

if (openParen == -1) {
    break;
}

int closeParen = markdown.indexOf(")", openParen);
```
Here should be a check for a new line character. If there is, then 
the link is invalid and it should start at the next open bracket. 

