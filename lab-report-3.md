# Command line arguments for find

## -name

I found the -name command from class.

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
