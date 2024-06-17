# DNA-Scrubbing

#  DNA-Testing
Implementing a program that identifies a person based on their DNA, per the below.

##  Run Command
example:- $ python dna.py databases/large.csv sequences/5.txt

## Specification
file called dna.py implements a program that identifies to whom a sequence of DNA belongs.

- The name of a text file containing the DNA sequence to be identified should be the second command-line argument, and the programme should require the name of a CSV file containing the STR counts for a list of individuals as its first command-line argument.
- - Your programme should print an error message of your choosing (using print) if it is run with the incorrect number of command-line arguments. You can presume that the first argument is, in fact, the filename of a legitimate CSV file and the second argument is the filename of a legitimate text file if the appropriate number of arguments is supplied.
- The CSV file should open in your programme, and its contents should be read into memory.
It is reasonable to assume that the column names will appear in the first row of the CSV file. The word name will appear in the first column, and the STR sequences themselves will appear in the subsequent columns.
- The DNA sequence should open in your programme, and its contents should be read into memory.
- Your programme should determine the longest run of consecutive repeats of each STR (found in the first line of the CSV file) for each DNA sequence it needs to identify.
- Your programme should print the name of the person whose STR counts exactly match any of the individuals in the CSV file.
- - You might think that there won't be more than one match for the STR counts.
Your programme should print "No match" if the STR counts do not exactly match any of the individuals in the CSV file.


## Usage
Your program should behave as per the example below:

$ python dna.py databases/large.csv sequences/5.txt
- Lavender

$ python dna.py
- Usage: python dna.py data.csv sequence.txt

$ python dna.py data.csv
- Usage: python dna.py data.csv sequence.txt

## Background
DNA, the carrier of hereditary data in living things, has been utilized in criminal equity for decades. But how, precisely, does DNA profiling work? Given a grouping of DNA, how can measurable agents distinguish to whom it has a place?

Well, DNA is truly fair a arrangement of particles called nucleotides, orchestrated into a specific shape (a twofold helix). Each nucleotide of DNA contains one of four diverse bases:
adenine (A), cytosine (C), guanine (G), or thymine (T). Each human cell has billions of these nucleotides organized in grouping. A few parcels of this arrangement (i.e. genome) are the same, or at slightest exceptionally comparative, over nearly all people, but other parcels of the arrangement have the next hereditary differing qualities and hence change more over the populace.

One put where DNA tends to have tall hereditary differing qualities is in Brief Tandem Repeats (STRs). An STR may be a brief arrangement of DNA bases that tends to rehash continuously various times at particular areas interior of a person's DNA. The number of times any specific STR rehashes changes a part among people. Within the DNA tests underneath, for illustration, Alice has the STR AGAT rehashed four times in her DNA, whereas Weave has the same STR rehashed five times.

Utilizing different STRs, instead of fair one, can progress the exactness of DNA profiling. On the off chance that the likelihood that two individuals have the same number of rehashes for a single STR is 5%, and the examiner looks at 10 diverse STRs, at that point the likelihood that two DNA tests coordinate simply by chance is almost 1 in 1 quadrillion (accepting all STRs are free of each other). So in the event that two DNA tests coordinate within the number of rehashes for each of the STRs, the investigator can be lovely sure they came from the same individual. CODIS, The FBI's DNA database, employments 20 diverse STRs as portion of its DNA profiling prepare.

What might such a DNA database look like? Well, in its least complex frame, you may envision designing a DNA database as a CSV record, wherein each push compares to an person, and each column compares to a specific STR.

name,AGAT,AATG,TATC
Alice,28,42,14
Bob,17,22,19
Charlie,36,18,25

The information within the over record would propose that Alice has the grouping AGAT rehashed 28 times sequentially some place in her DNA, the arrangement AATG rehashed 42 times, and TATC rehashed 14 times. Sway, in the mean time, has those same three STRs rehashed 17 times, 22 times, and 19 times, individually. And Charlie has those same three STRs rehashed 36, 18, and 25 times, separately.

So given a grouping of DNA, how might you recognize to whom it has a place? Well, envision merely looked through the DNA arrangement for the longest continuous grouping of rehashed AGATs and found that the longest grouping was 17 rehashes long. On the off chance that you at that point found that the longest arrangement of AATG is 22 rehashes long, and the longest arrangement of TATC is 19 rehashes long, that would give beautiful great prove that the DNA was Bob's. Of course, it's too conceivable that once you take the tallies for each of the STRs, it doesn't coordinate anybody in your DNA database, in which case you have no coordinate.

In hone, since examiners know on which chromosome and at which area within the DNA an STR will be found, they can localize their look to fair a contract segment of DNA. But we'll disregard that detail for this issue.

 
