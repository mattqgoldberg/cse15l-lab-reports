# Command line arguments for grep

## -v

Found this command at the following link.
[Link] ([https://man7.org/linux/man-pages/man1/find.1.html](https://en.wikibooks.org/wiki/Grep))

Example 1:

`[cs15lwi23ann@ieng6-202]:skill-demo1-data:216$ find ./written_2 -name "*History.txt"
./written_2/travel_guides/berlitz2/Algarve-History.txt
./written_2/travel_guides/berlitz2/Amsterdam-History.txt
./written_2/travel_guides/berlitz2/China-History.txt
./written_2/travel_guides/berlitz2/Costa-History.txt
./written_2/travel_guides/berlitz2/CostaBlanca-History.txt
./written_2/travel_guides/berlitz2/Crete-History.txt
./written_2/travel_guides/berlitz2/Cuba-History.txt
./written_2/travel_guides/berlitz2/Nepal-History.txt
./written_2/travel_guides/berlitz2/NewOrleans-History.txt
./written_2/travel_guides/berlitz2/Poland-History.txt
./written_2/travel_guides/berlitz2/Portugal-History.txt
./written_2/travel_guides/berlitz2/PuertoRico-History.txt
./written_2/travel_guides/berlitz2/Vallarta-History.txt
[cs15lwi23ann@ieng6-202]:skill-demo1-data:217$
`

The -name argument finds all files that have the name pattern in the argument. In this case "*History.txt" finds all files in written_2 that have file names ending with History.txt.

Example 2:

`[cs15lwi23ann@ieng6-202]:skill-demo1-data:218$ find ./written_2 -name "Bahamas*To*"
./written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
./written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
`

This command is similar to the one above, but it finds all files starting with Bahamas, with something in between represented by a *, then the word To, then anything after represented by *.

## -iname

Found this command at the following link.
[Link] (https://man7.org/linux/man-pages/man1/find.1.html)

Example 1:

`[cs15lwi23ann@ieng6-202]:skill-demo1-data:219$ find ./written_2 -iname "Bahamas*To*"
./written_2/travel_guides/berlitz2/Bahamas-History.txt
./written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
./written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
[cs15lwi23ann@ieng6-202]:skill-demo1-data:220$
`

-iname is similar to -name but it is not case-sensitive. You will notice that the command is identical to the second example for -name except it uses -iname. Because this ignores case it outputs an additional file Bahamas-History.txt because the 'to' in history matches the pattern in the command argument if case is ignored.

Example 2:

`[cs15lwi23ann@ieng6-202]:skill-demo1-data:222$ find ./written_2 -iname "HISTORY*"
./written_2/travel_guides/berlitz1/HistoryDublin.txt
./written_2/travel_guides/berlitz1/HistoryEdinburgh.txt
./written_2/travel_guides/berlitz1/HistoryEgypt.txt
./written_2/travel_guides/berlitz1/HistoryFWI.txt
./written_2/travel_guides/berlitz1/HistoryFrance.txt
./written_2/travel_guides/berlitz1/HistoryGreek.txt
./written_2/travel_guides/berlitz1/HistoryHawaii.txt
./written_2/travel_guides/berlitz1/HistoryHongKong.txt
./written_2/travel_guides/berlitz1/HistoryIbiza.txt
./written_2/travel_guides/berlitz1/HistoryIndia.txt
./written_2/travel_guides/berlitz1/HistoryIsrael.txt
./written_2/travel_guides/berlitz1/HistoryIstanbul.txt
./written_2/travel_guides/berlitz1/HistoryItaly.txt
./written_2/travel_guides/berlitz1/HistoryJamaica.txt
./written_2/travel_guides/berlitz1/HistoryJapan.txt
./written_2/travel_guides/berlitz1/HistoryJerusalem.txt
./written_2/travel_guides/berlitz1/HistoryLakeDistrict.txt
./written_2/travel_guides/berlitz1/HistoryLasVegas.txt
./written_2/travel_guides/berlitz1/HistoryMadeira.txt
./written_2/travel_guides/berlitz1/HistoryMadrid.txt
./written_2/travel_guides/berlitz1/HistoryMalaysia.txt
./written_2/travel_guides/berlitz1/HistoryMallorca.txt
`

This example finds all of the files in written_2 that begin with history. Notice that history is in all caps in the command, but it finds all of the files with history in any case because -iname is not case-sensitive.

## -size

Example 1:

Found this command at the following link.
[Link] (https://man7.org/linux/man-pages/man1/find.1.html)

`[cs15lwi23ann@ieng6-202]:skill-demo1-data:239$ find ./written_2 -size -1000c
./written_2/travel_guides/berlitz1/HandRIbiza.txt
./written_2/travel_guides/berlitz1/HandRIstanbul.txt
`

The -size argument finds all files less than, equal to, or greater than the size input. The argument -1000c, finds all files in written_2 that are smaller than 1000 bytes, which found two files.

Example 2:

`[cs15lwi23ann@ieng6-202]:skill-demo1-data:240$ find ./written_2 -size 1000c`

This command gives no output, because there is no + or - sign in front of the size argument. This means it only matches files that are EXACTLY 1000 bytes in size which there are none in written_2 so find finds nothing here.

## -path

Found this command at the following link.
[Link] (https://man7.org/linux/man-pages/man1/find.1.html)

Example 1:

`[cs15lwi23ann@ieng6-202]:skill-demo1-data:244$ find ./written_2 -path */berlitz1/*ToI*
./written_2/travel_guides/berlitz1/WhatToIbiza.txt
./written_2/travel_guides/berlitz1/WhatToIndia.txt
./written_2/travel_guides/berlitz1/WhatToIsrael.txt
./written_2/travel_guides/berlitz1/WhatToIstanbul.txt
./written_2/travel_guides/berlitz1/WhatToItaly.txt
./written_2/travel_guides/berlitz1/WhereToIbiza.txt
./written_2/travel_guides/berlitz1/WhereToIndia.txt
./written_2/travel_guides/berlitz1/WhereToIsrael.txt
./written_2/travel_guides/berlitz1/WhereToIstanbul.txt
./written_2/travel_guides/berlitz1/WhereToItaly.txt
`

The -path argument is very similar to the -name arugment, but it includes the entire path in the search for matching patterns. Here we find all files whose path contains /berlitz1/ and ToI, which finds 10 files in the folder berlitz1.

Example 2:

`[cs15lwi23ann@ieng6-202]:skill-demo1-data:260$ find ./written_2 -path *non-fiction*Kauffman*
./written_2/non-fiction/OUP/Kauffman
./written_2/non-fiction/OUP/Kauffman/ch1.txt
./written_2/non-fiction/OUP/Kauffman/ch10.txt
./written_2/non-fiction/OUP/Kauffman/ch3.txt
./written_2/non-fiction/OUP/Kauffman/ch4.txt
./written_2/non-fiction/OUP/Kauffman/ch5.txt
./written_2/non-fiction/OUP/Kauffman/ch6.txt
./written_2/non-fiction/OUP/Kauffman/ch7.txt
./written_2/non-fiction/OUP/Kauffman/ch8.txt
./written_2/non-fiction/OUP/Kauffman/ch9.txt`

This command files all files whose path contain non-fiction and Kauffman, which returns only the file finds the Kauffman folder and all of the files inside of it.


