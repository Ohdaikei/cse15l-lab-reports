# CSE15L Lab Report 3

## Researching commands

In the last lab, we used several practical command lines, among which I would like to introduce the command `grep`. `grep` is a command to search for particular strings in files.　However, grep can be very useful or sometimes difficult to use, depending on how it is used. I will introduce some of the useful command-line options which would help finding more efficiently.

First, as used in the skill-demonstration, let's find the string "Lucayans" in the txt files inside the directory `./written_2`(However, we already know where "Lucayans" is stored, it is in the `Bahamas-History.txt`).

```
grep Lucayans written_2
```
The out put will be 
```
grep: written_2: Is a directory
```

It caused an error. The reason is the files under `./written_2` are all directories. The command can find the string under .txt files so we have to fix it. Instead, I will add the path along `Bahamas-History.txt`.
```
grep Lucayans written_2/travel_guides/berlitz2/Bahamas-History.txt
```
The output will be
```
Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```

It showed a lot of words! The output is the whole text of the line which includes "Lucayans". We were able to find where "Lucayans" in the `Bahamas-History.txt` file, but it is only useful in a limited situation. How can I look up without knowing the file path.
In that point, we can add `-r` after `grep`. This command allows us to search for strings inside subdirectories.

```
grep -r Lucayans written_2
```
The output will be
```
written_2/travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
written_2/travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```

This seems much more useful than before. We can know which file stores the string "Lucayans". We can try other arbitrary string "dictionary", for example.
```
grep -r dictionary written_2
```
Output:
```
written_2/non-fiction/OUP/Kauffman/ch6.txt:The dictionary hints at where our reductionism ideas may go wrong: Every word in the dictionary is defined in terms of other words. How could it be otherwise? Concepts are defined in webs, somehow tacked onto the real world by ostensive definitions = definitions given by pointing to examples. We carve up the world in a variety of ways, Wittgenstein’s language games, that appear not to be reducible to one another in the strict sense of necessary and suYcient conditions. And this, in turn, underlies the question whether legal systems and human actions are parts of the furniture of the universe, somehow above or in addition to the locations and motions of atoms and fields.
written_2/non-fiction/OUP/Castro/chC.txt:One published dictionary of caló, by Jay Rosensweig, presents caló in a rather harsh manner, referring to it as gutter Spanish, which prompted a reader to take the privilege of writing a comment on the title page of the book. This example of “book graffiti” is presented here because it is an excellent example of the use of Chicano Spanish influenced by caló and used at an opportune moment:
written_2/non-fiction/OUP/Castro/chM.txt:The Spanish dictionary definition of manda is a “proposal” or an “offer.” It comes from the verb mandar, meaning “to order” or “to command,” and the phrase mandar hacer means “to have made” or “to command to be made.” In folk religious practices a manda is interpreted as a promise or contract made with a saint, the Virgin Mary, or God. The contract is not a legal commitment nor made with the approval of a priest or the Catholic Church. It is purely a personal promise made to fulfill or complete a journey, a devotional act, or to recite a certain number of prayers. This promise is in exchange for the curing of an illness or for a solution to a problem. The manda may involve the placing of a milagro (symbol of a miracle) at the shrine of a saint, La Virgen de Guadalupe cathedral in Mexico City for example, or the lighting of candles at the local church. Although the fulfillment of the manda in itself may not be difficult, its completion often involves some sacrifice, and this aspect is also considered part of the manda. Lighting daily candles could be a financial strain, and a pilgrimage may take several years to complete, yet neither is ever forgotten, and a manda is taken more seriously than a legal written contract. There may be fear of retribution from a saint if the manda is not fulfilled, and sometimes individuals actually suffer this retribution. If a woman makes a manda asking for a cure to her child’s illness and the child is cured but she does not complete the manda, the child may become ill again. The woman will believe the second illness was caused because she did not complete her manda. A manda may be completed after the request is fulfilled in thanksgiving, or it may be fulfilled before the petition is answered, with the assumption that it will be answered. Mandas are very private and often only very close family members are aware that a person has made one.
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt:In an attractive garden setting, the large Ursuline Convent was established in 1639 and rebuilt twice after fire. Its chapel has a fine 18th-century altar painting and pulpit. Montcalm was buried here after the battle, but only his skull remains, in a museum otherwise devoted to the convent’s first mother superior, who compiled the first dictionary of the Iroquois and Algonquin languages. The pasture for the convent’s cattle is now the quiet, spacious Parc de l’Esplanade, the perfect place to rest your tired sightseeing feet.
```

Still lots of words but we could find where the string is stored. But isn't it there more clear and easy way to know only the names of the file? In this case, we can use `-l` at the same time as the one we just used. We write the command `-rl` instead of simply write side by side.

```
grep -rl Lucayans written_2
```
Output:
```
written_2/travel_guides/berlitz2/Bahamas-History.txt
```
dictionary case:
```
grep -rl dictionary written_2
```
Output:
```
written_2/non-fiction/OUP/Kauffman/ch6.txt
written_2/non-fiction/OUP/Castro/chC.txt
written_2/non-fiction/OUP/Castro/chM.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
```

We are able to know only the file names which contains "Lucayans" and "dictionary" respectively. This method might have been applied to a search engine.

Finally, I would like to introduce a command which might be helpful in a different case. The command-line I will use is `-n`. Let's see what would this command will do.
```
grep -n Lucayans written_2/travel_guides/berlitz2/Bahamas-History.txt 
```
Output:
```
6:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
7:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```

By using `-n`, the line number is also output. How can this could applied? Let's try using `-no`.
```
grep -no Lucayans written_2/travel_guides/berlitz2/Bahamas-History.txt
```
Output:
```
6:Lucayans
7:Lucayans
```

The output is very simple and easy to read. I think this method can be helpful when finding things in a table(I understand that there must have a more efficient algorithm to find things in a table).
I found these methods in a Japanese website which lists the main usage of `grep` commands.

