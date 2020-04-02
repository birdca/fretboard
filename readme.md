# Fretboard

Fretboard is a simple platform that lets you create SVG versions of guitar chord and scale charts via raw ASCII text. Currently in progress. For more info, see: http://davidpots.com/blog/guitar-fretboard-ascii-svg/

## Documentation

Mainly for my own reference.

### Basic ASCII-to-SVG Setup
Use this basic HTML format. You must specify either `v4`, `v5`, `v7`, `v9`, `v12`, or `v15` as a class in the `.asciiFret` element. Also, the spacing of the fretboard needs to account for 6 strings, with a space of padding buffering all characters.

    <div class="fretboard_instance">
    <pre class="asciiFret v4">
     x  ^ ^ 
     ||||o| 
     ||o||| 
     |o|||| 
     |||||| 
            
    </pre>
    </div>

Here is each ASCII character that is supported for replacement. Each character is replaced by a SVG cell of uniform sizing. These cells are overlayed onto an SVG fretboard.

    " " becomes an empty cell
    "|" becomes an empty cell
    "^" becomes an 'open' string indicator cell
    "x" becomes an 'muted' string indicator cell
    "o" becomes a finger cell (single finger)
    "(" becomes a finger cell (left edge of a barre chord)
    ")" becomes a finger cell (right edge of a barre chord)
    "=" becomes a finger cell (middle of a barre chord)

### No Nut
If you want to show a fretboard that is agnostic with respect to where it is relative to the nut of the guitar (i.e., the top of the guitar where the 0th fret would be), add class `.noNut` to the `.asciiFret` div.

### renderFretBoard() API
#### Concept
Input data like:
```
title: horizontal, 5 frets
type: h6 noNut
        
 -oO-*- 
 --o-o- 
 -o-oo- 
 -o-oO- 
 -oo-o- 
 -*O-o- 
```
will generate html string.

#### Details
There are 3 parts of input data:
1. title: fretboard title
2. type: fretboard type, supporting for:
    a. vertical: supporting for fret 4, 5, 7, 9, 12 and 15. The code is: v4, v5, v7, v9, v12, v15
    b. horizontal: supporting for fret 5, 6 and 7. The code is: h5, h6, h7
    c. noNut: default value is has nut, type **noNut** in type if you don't want to show nut. ex. type: h6 noNut
3. [ascii fret](https://github.com/birdca/fretboard#basic-ascii-to-svg-setup)

### More coming soon... 
Stay tuned.