txt2cwp
=======

Create a simple textfile containing only a filled out crossword form.
Filled blocks in the puzzle are set by the character '`_`' (underscore).
You don't have to set up the dimension of the puzzle - just put the same
number of letters into each line.

If you look at the example in 'cwp.txt' you will find its content to be:

`counter`
`hex_rsa`
`amt_and`
`r_esc__`
`_friend`
`vim__or`

It is very easy to fill such a puzzle if you start with something like this:

`counter`
`..x....`
`..t....`
`..e....`
`..r....`
`..m....`

and fill in the missing letters in replace (overwrite) mode in your editor.

Then you can parse the source file through txt2cwp:

`txt2cwp cwp.txt`

This generates cwp.tex, a frameset for your puzzle in which only the clues are missing.
You have to insert the clues into the tex file at the appropriate positions:

  `\Clue{1}{counter}{}%`
  `\Clue{7}{hex}{}%`

will become something like this:

  `\Clue{1}{counter}{Something increasing each time around}%`
  `\Clue{7}{hex}{Regular polygon with the most vertices to tile a plane with}%`

Since the solution to each clue is given as second parameter to \Clue,
this should be very easy, in fact, dare I say, comfortable!

After all the clues are added compile the tex file using:

  `pdflatex cwp.tex`

and you are done...

Enjoy!
