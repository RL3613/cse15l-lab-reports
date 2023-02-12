# Lab Report 3
## Grep Command
By default, grep works as follows:

`grep "text" file.txt`

This will display all instances of the String `text` in the file `file.txt`. This may appear as a substring, and is case sensitive.

We will now explore different options of `grep`.

### `grep -i`
Syntax: `grep -i "text" file.txt`

The `-i` flag removes case sensitivity from `grep`, so any uppercase and lowercase permutations of `tExT` will be found.

#### Example 1
```console
grep -i "Land" HandRHawaii.txt
```

Produces the following results:
```console
Matson steamship line, has been a landmark since it opened in 1927 on
Ohana Maui Islander $$ 660 Wainee Street, Lahaina, HI
Big Island of Hawaii
away is one of the island’s best snorkeling and swimming beaches. 311
lava on the Kohala Coast. It was lauded as the best island resort in
of the island, Ke Nani Kai consists of spacious fully-appointed
horse ranch on the west side of the island, this is Molokai’s most
```

Even though the search is "Land", we are still able to find mentions of lowercase "land". This is useful if we want to find all instances of "land" in this text.

#### Example 2
```console
grep -i "egypt" HistoryIsrael.txt
```

Produces the following results:
```console
fought the ruling Egyptians. Eventually famine compelled Abraham’s
tribes to move into Egypt and into captivity. In about 1250 b.c. ,
Akko fell to the Egyptian Mamelukes (freed slaves of
with the new state engaged in fighting the combined armies of Egypt,
combined Israeli-French and British attack on Egypt, and the start of
international pressure forced Israel to withdraw — with Egypt
Egypt, Syria, Jordan, and Iraq with a preemptive strike. The war was
Jerusalem, Gaza, and the West Bank, as well as Egypt’s Sinai and
Attempting to regain the Sinai and the Golan, Egypt and
Egypt and Israel made an important movement towards a
```

We search for "egypt", but because we had `-i`, we are able to find the String "Egypt" in the text. Without it, we would have to type Egypt exactly like so in order to find mentions of the country. We may even think there are no mentions of Egypt whatsoever.

### `grep -w`
Syntax: `grep -w "text" file.txt`

This will display all instances of exactly the word "text" in file.txt. It will not include words that include "text", such as "texture" or "textile".

#### Example 1
```console
grep -w "Egypt" HistoryIsrael.txt
```

Produces the following results:
```console
tribes to move into Egypt and into captivity. In about 1250 b.c. ,
with the new state engaged in fighting the combined armies of Egypt,
combined Israeli-French and British attack on Egypt, and the start of
international pressure forced Israel to withdraw — with Egypt
Egypt, Syria, Jordan, and Iraq with a preemptive strike. The war was
Jerusalem, Gaza, and the West Bank, as well as Egypt’s Sinai and
Attempting to regain the Sinai and the Golan, Egypt and
Egypt and Israel made an important movement towards a
```

This will display all instances of the word "Egypt", but will exclude "Egyptian" and "Egyptians". Notice that "Egypt's" is still included. This is useful for finding mentions of the country as a noun, but not as an adjective.

#### Example 2
```console
grep -w "I" IntroItaly.txt
```

Produces the following results:
```console
Vittorio Emanuele II and his son Umberto I.
Vecchio in the Piazza della Signoria, Duke Cosimo I and his wife,
here, in exile, in 1321, with a fellow poet’s epitaph: “Here I lie
Renaissance palazzi of the Corso Ercole I d’Este, part of a
residence of Vittorio Amedeo I’s widow, nicknamed “Madama Reale,” a.k.a
Traffic roars down the broad Corso Umberto I to the
Umberto I, opposite the great Neoclassical temple of Neapolitan bel
Piazza Umberto I) where the funicular lets you off. Many day trippers
Sicily’s Norman king, Roger I, and to the left, his admiral, Georges of
run naked into the street crying “Eureka” (I have it! ).
```

If we had searched "I" without `-w`, we would have obtained a much longer list that includes words like "Its", "If", et cetera. This would be bad if we are looking for the pronoun "I". Using `-w`, we were mostly able to filter out instances where "I" is not used as a first-person pronoun.

### `grep -n`
Syntax: `grep -n "text" file.txt`

This will display all instances of "text" and the lines at which they occur in file.txt.

#### Example 1
```console
grep -n "ocean" WhatToJamaica.txt
```

Produces the following results:
```console
620:        tropical vegetation reach out into the ocean. Beautiful private villas
643:        millions of years ago, when this area lay on the ocean floor. The paths
1140:        directly into the clear blue ocean. The town has passed planning
```

This will allow us to know exactly where "ocean" is located in WhatToJamaica.txt when we open up the file in a text editor. It allows us to find what we want easily.

#### Example 2
```console
grep -win "water" WhereToGreek.txt
```

Produces the following results:
```console
85:        Greek. Its islands have small fishing harbors replete with azure water,
128:        balconies overhanging the water. Known as the Alefkandra Quarter or
130:        dinner by the water’s edge. From here, you’ll get a full view of the
182:        stagnant water. Walking through the site toward the palm tree will take
298:        Chorio, has fresh spring water fountains which are still used by hill
299:        farmers to collect water for their homes. Village households still wash
364:        resort has a large park featuring water slides and a children’s play
430:        water supplies offer a cool and fragrant break from the heat of the
460:        years afterwards. In place of land came water, surging in to fill the
482:        down toward the water with stunning views. A narrow cobbled trail of
558:        Some of the best views of Santorini are from the water. Try
603:        the Castle of the Knights of St. John at the water’s edge. It still
961:        water to the ancient capital. The Tunnel of Eupalinos can be explored
1033:        watched the Battle of Troy taking place, looking east across the water.
```
When we use `-win`, we are applying `-i`, -`w`, and `-n` all at the same time. Now we search for the word "water" in isolation, in capital or lowercase, and we can see which lines all these instances are at.

### `grep -r`
Syntax: `grep -r "text" directory`

Normally, if we try to use grep on a directory, we are met with the message `grep: directory: Is a directory`. By using `-r`, we tell the computer to search through all the files within the directory recursively and find instances of "text". It will also tell us which file each instance appears in.

#### Example 1
Here, I have changed my directory to written_2.
```console
grep -r "suspicious" .
```
Note: the `.` is a shorthand for current directory.

Produces the following results:
```console
./non-fiction/OUP/Kauffman/ch9.txt:But we have seen grounds to be deeply suspicious of the claim that we can finitely prestate all possible exaptations  whether they be new organic functionalities or new goods  that arise in a biosphere or an econosphere, such as Gertrude learning to fly in her terrified leap from the pine tree million years ago last Friday or the engineers working on the tractor suddenly realizing that the engine block itself could serve as the chassis.
./travel_guides/berlitz1/HistoryEdinburgh.txt:        the English crown, and Elizabeth was suspicious of her intentions.
./travel_guides/berlitz1/WhereToJapan.txt:        shogunate, always suspicious of people on the move, maintained a system
```
This is useful if we want to find sussy activities in all of history, and we have a directory of history files.

#### Example 2
```console
grep -r "derivative" .
```

Produces the following results:
```console
./travel_guides/berlitz1/WhatToMalaysia.txt:        Another derivative of the game, using a different kind of top, has for
./travel_guides/berlitz2/Canada-WhereToGo.txt:The McMichael Canadian Collection (in the village of Kleinburg, 25 km/15 miles, 40 minutes’ drive, northwest of Toronto) consecrates the work of one of Canada’s best-known schools of painting, the Group of Seven. These artists of the first half of the 20th century sought the sources of their inspiration in a distinctly Canadian landscape rather than in the derivative themes of European painting. The museum has chosen an appropriate setting of evergreen forest overlooking the Humber valley for its location. The stone and log building is itself, in more solid form, a visual reference to the log cabins of the country’s earliest settlers. Look out, too, for the Inuit and Indian art, most notably the work of Norval Morrisseau, a Midéwiwin Indian from northern Ontario whose works explore traditional subjects with a modern abstract technique.
```
Once again, we see that we find the word "derivative" in multiple files in our directory.

## Works Cited
* https://www.youtube.com/watch?v=VGgTmxXp7xQ
