# Command line arguments for less

All of the arguemnts for the less command in this report I found by running `less --help` in my terminal.

The less command allows you to read files through the terminal using the up and down arrow keys to scroll as well as many other features.
## Command argument 1: -r


The first thing I noticted when using less to read a file is that I was getting weird symbols in my files.
For example:
`less HistoryFrance.txt` gives the following output:

`A BRIEF HISTORY
        The French have always wanted to know what it means to be
        a<E2><80><82>French<C2><AD>man. Their history has been a constant quest for national
        identity: a conflict between strong regional loyalties and central
        authority.
        In about 2000<E2><80><82>b.c. Celtic tribes <E2><80><94> probably from eastern
        Europe <E2><80><94> came looking for greener pastures in the areas that are now
        Franche-Comt<C3><A9>, Alsace, and Bur<C2><AD>gundy. At the same time, migrants from
        the Mediterranean countries were trickling into the south.
        The first recorded settlement was the trading post set up by
        Phocaean Greeks from Asia Minor at Massalia (Mar<C2><AD>seilles) around
        600<E2><80><82>b.c. , followed by other ports at Hy<C3><A8>res, Antibes, and Nice. But
        the Greeks developed few contacts with the interior beyond a little
        commerce in olives and wine with the Celts of Burgundy. When their
        position was threatened by Ligurian pirates at sea and warlike tribes
        from inland, the merchants of Marseilles called on Rome for help.
        From Gaul to France
        In 125<E2><80><82>b.c. , the Romans came in force, conquered the
        <E2><80><9C>Gallic barbarians,<E2><80><9D> and set up a fortress at Aquae Sextiae
HistoryFrance.txt
`

These weird characters like `<E2><80><82>` are not present in the actual file and an issue with less.
Rerunning the command using the -r option or `less -r HistoryFrance.txt` fixes the output like this:

`
A BRIEF HISTORY
        The French have always wanted to know what it means to be
        a French­man. Their history has been a constant quest for national
        identity: a conflict between strong regional loyalties and central
        authority.
        In about 2000 b.c. Celtic tribes — probably from eastern
        Europe — came looking for greener pastures in the areas that are now
        Franche-Comté, Alsace, and Bur­gundy. At the same time, migrants from
        the Mediterranean countries were trickling into the south.
        The first recorded settlement was the trading post set up by
        Phocaean Greeks from Asia Minor at Massalia (Mar­seilles) around
        600 b.c. , followed by other ports at Hyères, Antibes, and Nice. But
        the Greeks developed few contacts with the interior beyond a little
        commerce in olives and wine with the Celts of Burgundy. When their
        position was threatened by Ligurian pirates at sea and warlike tribes
        from inland, the merchants of Marseilles called on Rome for help.
        From Gaul to France
        In 125 b.c. , the Romans came in force, conquered the
        “Gallic barbarians,” and set up a fortress at Aquae Sextiae
HistoryFrance.txt
`

## Command Argument 2: -N

running `less -r -N HistoryFrance.txt` displays the following output:
`
  1
      2
      3
      4
      5
      6         A BRIEF HISTORY
      7         The French have always wanted to know what it means to be
      8         a French­man. Their history has been a constant quest for national
      9         identity: a conflict between strong regional loyalties and central
     10         authority.
     11         In about 2000 b.c. Celtic tribes — probably from eastern
     12         Europe — came looking for greener pastures in the areas that are now
     13         Franche-Comté, Alsace, and Bur­gundy. At the same time, migrants from
     14         the Mediterranean countries were trickling into the south.
     15         The first recorded settlement was the trading post set up by
     16         Phocaean Greeks from Asia Minor at Massalia (Mar­seilles) around
     17         600 b.c. , followed by other ports at Hyères, Antibes, and Nice. But
     18         the Greeks developed few contacts with the interior beyond a little
     19         commerce in olives and wine with the Celts of Burgundy. When their
     20         position was threatened by Ligurian pirates at sea and warlike tribes
     21         from inland, the merchants of Marseilles called on Rome for help.
     22         From Gaul to France
     23         In 125 b.c. , the Romans came in force, conquered the
     24         “Gallic barbarians,” and set up a fortress at Aquae Sextiae
`

This command adds line numbers to the output so you can see exactly where you are in the file.

## Command Argument 3: -s

I added a bunch of new lines to the HistoryFrance.txt files and running `less -r -N HistoryFrance.txt`
gives this output:

`A BRIEF HISTORY
      7         The French have always wanted to know what it means to be
      8         a French­man. Their history has been a constant quest for national
      9         identity: a conflict between strong regional loyalties and central
     10         authority.
     11         In about 2000 b.c. Celtic tribes — probably from eastern
     12         Europe — came looking for greener pastures in the areas that are now
     13         Franche-Comté, Alsace, and Bur­gundy. At the same time, migrants from
     14         the Mediterranean countries were trickling into the south.
     15
     16
     17
     18
     19
     20
     21
     22
     23         The first recorded settlement was the trading post set up by
     24         Phocaean Greeks from Asia Minor at Massalia (Mar­seilles) around
     25         600 b.c. , followed by other ports at Hyères, Antibes, and Nice. But
     26         the Greeks developed few contacts with the interior beyond a little
     27         commerce in olives and wine with the Celts of Burgundy. When their
`

Using the -s argument the output is different, with `less -r -N HistoryFrance.txt` showing:

`     6         A BRIEF HISTORY
      7         The French have always wanted to know what it means to be
      8         a French­man. Their history has been a constant quest for national
      9         identity: a conflict between strong regional loyalties and central
     10         authority.
     11         In about 2000 b.c. Celtic tribes — probably from eastern
     12         Europe — came looking for greener pastures in the areas that are now
     13         Franche-Comté, Alsace, and Bur­gundy. At the same time, migrants from
     14         the Mediterranean countries were trickling into the south.
     15
     23         The first recorded settlement was the trading post set up by
     24         Phocaean Greeks from Asia Minor at Massalia (Mar­seilles) around
     25         600 b.c. , followed by other ports at Hyères, Antibes, and Nice. But
     26         the Greeks developed few contacts with the interior beyond a little
     27         commerce in olives and wine with the Celts of Burgundy. When their
 `
 
 The -s argument compacts all of these extra new lines together and just shows one empty line between the two.
 It also acknolwedges these skipped lines in the line numbers on the side skipping from line 15 to line 23.


I wanted to include -D for my last command argument because it changes the colors of the less output but it only works on MS-DOS or at least I couldn't figure out how to get it work.

I did find that there are a lot of keyboard shortcuts within less itself that are very useful.

Pressing g takes you to the top of the file.
Pressing G takes you to the bottom of the file.

:e or ^X^V allows you to enter a new file to look at in less.

Other arguments like --mouse allows less to scroll using the mouse scroll wheel but I could not get this to work on my computer either.
