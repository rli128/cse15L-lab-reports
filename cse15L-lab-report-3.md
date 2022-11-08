Ricky Li
Joe Politz
31 October 2022

### CSE 15L Lab Report 3

# Less

The less command allows you to look at the contents of a file. You can scroll through the file using the arrow keys and exit the less command by pressing -q

## -N
```

1
      2
      3
      4
      5
      6         People living with HIV/AIDS (PLWA) face many forms of stigma and discrimination. This is
      7         the case in whichever country they may live, as has been shown in a number of previous
      8         research studies. In addition to experiencing unfair treatment in their families,
      9         communities, and places of work, PLWA may encounter discrimination from health-care
     10         professionals. This can interfere with effective prevention and treatment. Discriminatory
     11         practices in the health-care sector may also appear to legitimize other forms of
     12         discrimination against PLWA.
     13         Vincent Iacopino and colleagues from the organization Physicians for Human Rights, in
     14         collaboration with researchers from Policy Project–Nigeria and the Center for the Right to
     15         Health (also in Nigeria) investigated the problem in Nigeria. With a population of roughly
     16         130 million, Nigeria is home to one in 11 of the 40 million PLWA worldwide. Around 6% of
     17         adult Nigerians are thought to be HIV-positive, and there will be an estimated 310,000 AIDS
     18         deaths this year. The indications are that infection rates will increase. Until now, little
     19         has been known about the nature and extent of discrimination against patients with HIV/AIDS
     20         in Nigeria.
     21         Trained interviewers conducted a cross-sectional questionnaire survey of 1,021 Nigerian
     22         health-care professionals in 111 health-care facilities in four of Nigeria's 36 states.
     23         Those sampled were 324 physicians, 541 nurses, and 133 midwives, and 23 health-care workers
     24         of unknown profession. Fifty-four percent of them worked in public tertiary care
     25         facilities. Many of the survey's results are worrying. Nine percent of professionals
     26         reported refusing to care for a patient with HIV/AIDS, and 9% said they had refused a
     27         patient with HIV/AIDS admission to a hospital. Fifty-nine percent agreed that PLWA should
     28         be on a separate ward, and 40% believed a person's HIV status could be determined by their
     29         appearance. Ninety-one percent agreed that staff should be informed when a patient was
     30         HIV-positive in order to protect themselves. Forty percent believed health-care
technical/plos/pmed.0020257.txt

```
less -N technical/plos/pmed.002057.txt

The -N option gives you the option to have line numbers on the left side of the file so that you have an easier time looking through the file. I used the -N file on the pmed.0020209.txt file and I saw that it contained 299 lines.

## -p

```

company. The scientist had read my articles on *whistleblowers* who had raised concerns about
        the undue influence of the pharmaceutical industry on American medicine My industry source
        had information for me about drug company practices, but—out of fear of career ruin—would
        only talk on the condition that I would conceal the scientist's identity.
        For the next year or so, I had repeated contacts with the scientist. As I listened to
        this researcher—and to the other medical *whistleblowers* that I continued to interview—it
        occurred to me that each *whistleblower* was like the proverbial blind man with a hand on the
        elephant. Each could describe one piece of the puzzle, but the full picture could only
        emerge by bringing these *whistleblowers* together.
        With an eye to focusing on the systemic problems that have allowed American medicine to
        be unduly influenced by industry, on May 15, 2005, I brought together five *whistleblowers*
        in Washington, D. C. I asked them each to tell their story and to suggest ways to restore
        objectivity to medicine and medical research.


        The *Whistleblowers*
        Four *whistleblowers* attended in person, and the anonymous industry scientist
        participated via speakerphone. The *whistleblowers* came from an extraordinary variety of
        different professional backgrounds.



            David Graham
            This Food and Drug Administration (FDA) safety officer raised concerns about the
            cardiovascular side effects of rofecoxib (Vioxx) and other Cox-2 inhibitors. He
            testified at a United States Senate Finance Committee hearing on rofexocib, the FDA,
            and Merck [1,2]. Graham attended the roundtable in his own personal capacity and was
            not representing the FDA.

              Each *whistleblower* was like the proverbial blind man with a hand on the
technical/plos/pmed.0020209.txt

```

less -pwhistleblower technical/plos/pmed.0020209.txt

The -p option highlights what you are looking for while you are using less. For the example above I typed less -pwhistleblower technical/plos/pmed.0020209.txt 

This highlighted all the "whistleblower" words in the file making them easier for me to see

## -X

```

ricky@LAPTOP-BEVOSNJM MINGW64 ~/Documents/GitHub/docsearch (main)
$ less -X technical/plos/pmed.0020226.txt

  
    
      
        
        Richard Smith's key suggestion [1] is that medical journals “should stop publishing        
        trials” and concentrate on “critically evaluating them.” This bold and radical suggestion  
        deserves wide debate. It's obvious that many medical journals are losing relevance as      
        vehicles for scientific information, but it's unclear what will save them. Even as journals
        strive to better enforce their conflicts-of-interest disclosure rules, drug companies will 
        strive to find or create other publication outlets that can communicate to physicians      
        precisely what advertisers wish to communicate. In sum, an unanticipated effect of purging 
        clinical trial reports from medical journals might be an even larger proliferation of frank
        advertising outlets and messages that might more effectively catch doctors' attentions.    
      



```


less -X technical/plos/pmed.0020226.txt

The -X option makes the contents of the file stay on the screen even after you leave less. Usually when you are in less and you press q, the contents of the file go away when the less command ends, but if you use the -X option, the contents will stay as shown above.

# Find

The find command allows you to search through files and directories

## -name

```

$ find technical/plos -name "*8.txt"
technical/plos/journal.pbio.0020028.txt
technical/plos/journal.pbio.0020068.txt
technical/plos/journal.pbio.0020148.txt
technical/plos/journal.pbio.0020228.txt
technical/plos/journal.pbio.0020348.txt
technical/plos/pmed.0010008.txt
technical/plos/pmed.0010028.txt
technical/plos/pmed.0010048.txt
technical/plos/pmed.0010058.txt
technical/plos/pmed.0010068.txt
technical/plos/pmed.0020018.txt
technical/plos/pmed.0020028.txt
technical/plos/pmed.0020048.txt
technical/plos/pmed.0020068.txt
technical/plos/pmed.0020088.txt
technical/plos/pmed.0020098.txt
technical/plos/pmed.0020118.txt
technical/plos/pmed.0020148.txt
technical/plos/pmed.0020158.txt
technical/plos/pmed.0020198.txt
technical/plos/pmed.0020208.txt
technical/plos/pmed.0020238.txt
technical/plos/pmed.0020258.txt
technical/plos/pmed.0020268.txt
technical/plos/pmed.0020278.txt

```

find technical/plos -name ".txt"


The -name option allows you to search for a file with that name. This is especially useful for when you are searching for a specific extension (.txt, .java) In the example above, I used the find -name option to find all the files in the plos directory ending with 8.txt.

## -size

```

$ find technical/plos -size -3k
technical/plos
technical/plos/pmed.0020028.txt
technical/plos/pmed.0020048.txt
technical/plos/pmed.0020082.txt
technical/plos/pmed.0020120.txt
technical/plos/pmed.0020157.txt
technical/plos/pmed.0020191.txt
technical/plos/pmed.0020192.txt
technical/plos/pmed.0020226.txt

```

find technical/plos -size -3k

The -size option allows you to search for a file based on size. You can use the +size option to find a file that is bigger than the argument or -size to find a file smaller. For the example above, I used -size -3k to find files smaller than 3 kilobytes 

## -mtime


find technical/plos -mtime +10

```

$ find technical/plos -size -3k
technical/plos
technical/plos/pmed.0020028.txt
technical/plos/pmed.0020048.txt
technical/plos/pmed.0020082.txt
technical/plos/pmed.0020120.txt
technical/plos/pmed.0020157.txt
technical/plos/pmed.0020191.txt
technical/plos/pmed.0020192.txt
technical/plos/pmed.0020226.txt

ricky@LAPTOP-BEVOSNJM MINGW64 ~/Documents/GitHub/docsearch (main)
$ find technical/plos -mtime +10
technical/plos
technical/plos/journal.pbio.0020001.txt
technical/plos/journal.pbio.0020010.txt
technical/plos/journal.pbio.0020012.txt
technical/plos/journal.pbio.0020013.txt
technical/plos/journal.pbio.0020019.txt
technical/plos/journal.pbio.0020028.txt
technical/plos/journal.pbio.0020035.txt
technical/plos/journal.pbio.0020040.txt
technical/plos/journal.pbio.0020042.txt
technical/plos/journal.pbio.0020043.txt
technical/plos/journal.pbio.0020046.txt
technical/plos/journal.pbio.0020047.txt
technical/plos/journal.pbio.0020052.txt
technical/plos/journal.pbio.0020053.txt
technical/plos/journal.pbio.0020054.txt
technical/plos/journal.pbio.0020063.txt
technical/plos/journal.pbio.0020064.txt
technical/plos/journal.pbio.0020067.txt
technical/plos/journal.pbio.0020068.txt
technical/plos/journal.pbio.0020071.txt
technical/plos/journal.pbio.0020073.txt
technical/plos/journal.pbio.0020100.txt
technical/plos/journal.pbio.0020101.txt
technical/plos/journal.pbio.0020105.txt
technical/plos/journal.pbio.0020112.txt
technical/plos/journal.pbio.0020113.txt
technical/plos/journal.pbio.0020116.txt
technical/plos/journal.pbio.0020121.txt
technical/plos/journal.pbio.0020125.txt
technical/plos/journal.pbio.0020127.txt
technical/plos/journal.pbio.0020133.txt
technical/plos/journal.pbio.0020140.txt
technical/plos/journal.pbio.0020145.txt
technical/plos/journal.pbio.0020146.txt
technical/plos/journal.pbio.0020147.txt
technical/plos/journal.pbio.0020148.txt
technical/plos/journal.pbio.0020150.txt
technical/plos/journal.pbio.0020156.txt
technical/plos/journal.pbio.0020161.txt
technical/plos/journal.pbio.0020164.txt
technical/plos/journal.pbio.0020169.txt
technical/plos/journal.pbio.0020172.txt
technical/plos/journal.pbio.0020183.txt
technical/plos/journal.pbio.0020187.txt
technical/plos/journal.pbio.0020190.txt
technical/plos/journal.pbio.0020206.txt
technical/plos/journal.pbio.0020213.txt
technical/plos/journal.pbio.0020214.txt
technical/plos/journal.pbio.0020215.txt
technical/plos/journal.pbio.0020216.txt
technical/plos/journal.pbio.0020223.txt
technical/plos/journal.pbio.0020224.txt
technical/plos/journal.pbio.0020228.txt
technical/plos/journal.pbio.0020232.txt
technical/plos/journal.pbio.0020241.txt
technical/plos/journal.pbio.0020262.txt
technical/plos/journal.pbio.0020263.txt
technical/plos/journal.pbio.0020267.txt
technical/plos/journal.pbio.0020272.txt
technical/plos/journal.pbio.0020276.txt
technical/plos/journal.pbio.0020297.txt
technical/plos/journal.pbio.0020302.txt
technical/plos/journal.pbio.0020306.txt
technical/plos/journal.pbio.0020307.txt
technical/plos/journal.pbio.0020310.txt
technical/plos/journal.pbio.0020311.txt
technical/plos/journal.pbio.0020337.txt
technical/plos/journal.pbio.0020346.txt
technical/plos/journal.pbio.0020347.txt
technical/plos/journal.pbio.0020348.txt
technical/plos/journal.pbio.0020350.txt
technical/plos/journal.pbio.0020353.txt
technical/plos/journal.pbio.0020354.txt
technical/plos/journal.pbio.0020394.txt
technical/plos/journal.pbio.0020400.txt
technical/plos/journal.pbio.0020401.txt
technical/plos/journal.pbio.0020404.txt
technical/plos/journal.pbio.0020406.txt
technical/plos/journal.pbio.0020419.txt
technical/plos/journal.pbio.0020420.txt
technical/plos/journal.pbio.0020430.txt
technical/plos/journal.pbio.0020431.txt
technical/plos/journal.pbio.0020439.txt
technical/plos/journal.pbio.0020440.txt
technical/plos/journal.pbio.0030021.txt
technical/plos/journal.pbio.0030024.txt
technical/plos/journal.pbio.0030032.txt
technical/plos/journal.pbio.0030050.txt
technical/plos/journal.pbio.0030051.txt
technical/plos/journal.pbio.0030056.txt
technical/plos/journal.pbio.0030062.txt
technical/plos/journal.pbio.0030065.txt
technical/plos/journal.pbio.0030076.txt
technical/plos/journal.pbio.0030094.txt
technical/plos/journal.pbio.0030097.txt
technical/plos/journal.pbio.0030102.txt
technical/plos/journal.pbio.0030105.txt
technical/plos/journal.pbio.0030127.txt
technical/plos/journal.pbio.0030129.txt
technical/plos/journal.pbio.0030131.txt
technical/plos/journal.pbio.0030136.txt
technical/plos/journal.pbio.0030137.txt
technical/plos/pmed.0010008.txt
technical/plos/pmed.0010010.txt
technical/plos/pmed.0010013.txt
technical/plos/pmed.0010021.txt
technical/plos/pmed.0010022.txt
technical/plos/pmed.0010023.txt
technical/plos/pmed.0010024.txt
technical/plos/pmed.0010025.txt
technical/plos/pmed.0010026.txt
technical/plos/pmed.0010028.txt
technical/plos/pmed.0010029.txt
technical/plos/pmed.0010030.txt
technical/plos/pmed.0010034.txt
technical/plos/pmed.0010036.txt
technical/plos/pmed.0010039.txt
technical/plos/pmed.0010041.txt
technical/plos/pmed.0010042.txt
technical/plos/pmed.0010045.txt
technical/plos/pmed.0010046.txt
technical/plos/pmed.0010047.txt
technical/plos/pmed.0010048.txt
technical/plos/pmed.0010049.txt
technical/plos/pmed.0010050.txt
technical/plos/pmed.0010051.txt
technical/plos/pmed.0010052.txt
technical/plos/pmed.0010056.txt
technical/plos/pmed.0010058.txt
technical/plos/pmed.0010060.txt
technical/plos/pmed.0010061.txt
technical/plos/pmed.0010062.txt
technical/plos/pmed.0010064.txt
technical/plos/pmed.0010066.txt
technical/plos/pmed.0010067.txt
technical/plos/pmed.0010068.txt
technical/plos/pmed.0010069.txt
technical/plos/pmed.0010070.txt
technical/plos/pmed.0010071.txt
technical/plos/pmed.0020002.txt
technical/plos/pmed.0020005.txt
technical/plos/pmed.0020007.txt
technical/plos/pmed.0020009.txt
technical/plos/pmed.0020015.txt
technical/plos/pmed.0020016.txt
technical/plos/pmed.0020017.txt
technical/plos/pmed.0020018.txt
technical/plos/pmed.0020019.txt
technical/plos/pmed.0020020.txt
technical/plos/pmed.0020021.txt
technical/plos/pmed.0020022.txt
technical/plos/pmed.0020023.txt
technical/plos/pmed.0020024.txt
technical/plos/pmed.0020027.txt
technical/plos/pmed.0020028.txt
technical/plos/pmed.0020033.txt
technical/plos/pmed.0020034.txt
technical/plos/pmed.0020035.txt
technical/plos/pmed.0020036.txt
technical/plos/pmed.0020039.txt
technical/plos/pmed.0020040.txt
technical/plos/pmed.0020045.txt
technical/plos/pmed.0020047.txt
technical/plos/pmed.0020048.txt
technical/plos/pmed.0020050.txt
technical/plos/pmed.0020055.txt
technical/plos/pmed.0020059.txt
technical/plos/pmed.0020060.txt
technical/plos/pmed.0020061.txt
technical/plos/pmed.0020062.txt
technical/plos/pmed.0020065.txt
technical/plos/pmed.0020067.txt
technical/plos/pmed.0020068.txt
technical/plos/pmed.0020071.txt
technical/plos/pmed.0020073.txt
technical/plos/pmed.0020074.txt
technical/plos/pmed.0020075.txt
technical/plos/pmed.0020082.txt
technical/plos/pmed.0020085.txt
technical/plos/pmed.0020086.txt
technical/plos/pmed.0020088.txt
technical/plos/pmed.0020090.txt
technical/plos/pmed.0020091.txt
technical/plos/pmed.0020094.txt
technical/plos/pmed.0020098.txt
technical/plos/pmed.0020099.txt
technical/plos/pmed.0020102.txt
technical/plos/pmed.0020103.txt
technical/plos/pmed.0020104.txt
technical/plos/pmed.0020113.txt
technical/plos/pmed.0020114.txt
technical/plos/pmed.0020115.txt
technical/plos/pmed.0020116.txt
technical/plos/pmed.0020117.txt
technical/plos/pmed.0020118.txt
technical/plos/pmed.0020120.txt
technical/plos/pmed.0020123.txt
technical/plos/pmed.0020140.txt
technical/plos/pmed.0020144.txt
technical/plos/pmed.0020145.txt
technical/plos/pmed.0020146.txt
technical/plos/pmed.0020148.txt
technical/plos/pmed.0020149.txt
technical/plos/pmed.0020150.txt
technical/plos/pmed.0020155.txt
technical/plos/pmed.0020157.txt
technical/plos/pmed.0020158.txt
technical/plos/pmed.0020160.txt
technical/plos/pmed.0020161.txt
technical/plos/pmed.0020162.txt
technical/plos/pmed.0020180.txt
technical/plos/pmed.0020181.txt
technical/plos/pmed.0020182.txt
technical/plos/pmed.0020187.txt
technical/plos/pmed.0020189.txt
technical/plos/pmed.0020191.txt
technical/plos/pmed.0020192.txt
technical/plos/pmed.0020194.txt
technical/plos/pmed.0020195.txt
technical/plos/pmed.0020196.txt
technical/plos/pmed.0020197.txt
technical/plos/pmed.0020198.txt
technical/plos/pmed.0020200.txt
technical/plos/pmed.0020201.txt
technical/plos/pmed.0020203.txt
technical/plos/pmed.0020206.txt
technical/plos/pmed.0020208.txt
technical/plos/pmed.0020209.txt
technical/plos/pmed.0020210.txt
technical/plos/pmed.0020212.txt
technical/plos/pmed.0020216.txt
technical/plos/pmed.0020226.txt
technical/plos/pmed.0020231.txt
technical/plos/pmed.0020232.txt
technical/plos/pmed.0020235.txt
technical/plos/pmed.0020236.txt
technical/plos/pmed.0020237.txt
technical/plos/pmed.0020238.txt
technical/plos/pmed.0020239.txt
technical/plos/pmed.0020242.txt
technical/plos/pmed.0020246.txt
technical/plos/pmed.0020247.txt
technical/plos/pmed.0020249.txt
technical/plos/pmed.0020257.txt
technical/plos/pmed.0020258.txt
technical/plos/pmed.0020268.txt
technical/plos/pmed.0020272.txt
technical/plos/pmed.0020273.txt
technical/plos/pmed.0020274.txt
technical/plos/pmed.0020275.txt
technical/plos/pmed.0020278.txt
technical/plos/pmed.0020281.txt

```

The -mtime option allows you to search for a file based on the time the file was last edited or modified. You can use + or - to signal whether you want to look for files updated after or before the past days. In the example above I used -mtime +10 which looked for files that have been updated more than 10 days ago.


# Grep

The grep command searches for a matching string in a file

## -r

```

$ grep -r cigarettes technical/biomed
technical/biomed/1471-2156-3-22.txt:        less than 2 packs of cigarettes in her lifetime and the
technical/biomed/1471-2156-3-22.txt:          the number of packs of cigarettes smoked daily multiplied
technical/biomed/1471-2156-3-22.txt:          cigarettes, 4 cigars, or 4 pipes full of tobacco was
technical/biomed/1471-2156-3-22.txt:          cigarettes. Tobacco usage was coded as a dichotomous
technical/biomed/1471-2407-2-31.txt:          education, and packyears of cigarettes smoked. Covariates
technical/biomed/1471-2407-2-31.txt:        have had more packyears of cigarettes (p < 0.001).
technical/biomed/1471-2407-2-31.txt:        were divided into tertiles of packyears of cigarettes
technical/biomed/1471-2458-2-18.txt:        intervals (CIs). As packyears of cigarettes smoked smoking
technical/biomed/1471-2466-1-1.txt:        smoked cigarettes. The risk factor for HIV transmission was
technical/biomed/1476-069X-2-7.txt:          cigarettes smoked during pregnancy), evidence placental
technical/biomed/1476-069X-2-7.txt:          average number daily cigarettes smoked during pregnancy).
technical/biomed/1476-069X-2-7.txt:        cigarettes per day than mothers in other categories of
technical/biomed/1478-7954-1-3.txt:          of cigarettes smoked per day were investigated in Exams
technical/biomed/1478-7954-1-3.txt:          included the number of cigarettes smoked, alcohol intake,
technical/biomed/1478-7954-1-3.txt:          of cigarettes smoked per day calculated for smokers;
technical/biomed/1478-7954-1-3.txt:          there was a decline over time in the cigarettes smoked.
technical/biomed/1478-7954-1-3.txt:          associated with weight, whereas cigarettes smoked were
technical/biomed/1478-7954-1-3.txt:          of cigarettes smoked was negatively associated with HDL.
technical/biomed/1478-7954-1-3.txt:          LDL. However, the number of cigarettes smoked was
technical/biomed/1478-7954-1-3.txt:          LDL and HDL concentrations, cigarettes smoked, and
technical/biomed/1478-7954-1-3.txt:        alcohol consumption, and cigarettes smoked. An advantage of
technical/biomed/1478-7954-1-3.txt:        Third, the effects of smoking 14 cigarettes per day at
technical/biomed/1478-7954-1-3.txt:        halving the average number of cigarettes smoked would
technical/biomed/bcr605.txt:            controls had ever smoked cigarettes (59% and 55%,
technical/biomed/rr172.txt:          Kentucky standard cigarettes (1R3F; University of
technical/biomed/rr37.txt:          substantial proportion reported ever smoking cigarettes

```

grep -r cigarettes technical/biomed

The -r option allows you to grep an entire directory instead of just one file. For the example above, I looked through the entire biomed directory for files containing the word "cigarettes"

## -l 

```

$ grep -l cigarettes technical/biomed/*
technical/biomed/1471-2156-3-22.txt
technical/biomed/1471-2407-2-31.txt
technical/biomed/1471-2458-2-18.txt
technical/biomed/1471-2466-1-1.txt
technical/biomed/1476-069X-2-7.txt
technical/biomed/1478-7954-1-3.txt
technical/biomed/bcr605.txt
technical/biomed/rr172.txt
technical/biomed/rr37.txt

```

grep -l cigarettes techincal/biomed/*

The -l option will grep for the given files but will only return the file names instead of the file name and the lines containing the string. For the example above, I grepped through all the files in the biomed directory containing "cigarettes". This way is a lot easier to read compared to the previous example.

## -e 

```

$ grep -e cigarettes -e carcinogenic technical/biomed/*
technical/biomed/1471-2105-3-26.txt:        tumors in animal carcinogenicity studies, and the
technical/biomed/1471-2156-3-22.txt:        carcinogenic insults is offered in a report by Schantz et
technical/biomed/1471-2156-3-22.txt:        less than 2 packs of cigarettes in her lifetime and the
technical/biomed/1471-2156-3-22.txt:        a family of transcription factors known to be carcinogenic.
technical/biomed/1471-2156-3-22.txt:          the number of packs of cigarettes smoked daily multiplied
technical/biomed/1471-2156-3-22.txt:          cigarettes, 4 cigars, or 4 pipes full of tobacco was
technical/biomed/1471-2156-3-22.txt:          cigarettes. Tobacco usage was coded as a dichotomous
technical/biomed/1471-2210-2-8.txt:        taken from the FDA rodent carcinogenicity database [ 35 ] .
technical/biomed/1471-2210-2-8.txt:        metabolites against carcinogenicity and mutagenicity
technical/biomed/1471-2407-2-31.txt:          education, and packyears of cigarettes smoked. Covariates
technical/biomed/1471-2407-2-31.txt:        have had more packyears of cigarettes (p < 0.001).
technical/biomed/1471-2407-2-31.txt:        were divided into tertiles of packyears of cigarettes
technical/biomed/1471-2407-3-4.txt:        "preconditioned" by chronic exposure to carcinogenic
technical/biomed/1471-2458-2-18.txt:        intervals (CIs). As packyears of cigarettes smoked smoking
technical/biomed/1471-2466-1-1.txt:        smoked cigarettes. The risk factor for HIV transmission was
technical/biomed/1472-6882-1-10.txt:        carcinogenic risk cited in the literature on aristolochic
technical/biomed/1472-6947-3-8.txt:            our understanding of the carcinogenic process, they
technical/biomed/1476-069X-2-7.txt:          cigarettes smoked during pregnancy), evidence placental
technical/biomed/1476-069X-2-7.txt:          average number daily cigarettes smoked during pregnancy).
technical/biomed/1476-069X-2-7.txt:        cigarettes per day than mothers in other categories of
technical/biomed/1478-7954-1-3.txt:          of cigarettes smoked per day were investigated in Exams
technical/biomed/1478-7954-1-3.txt:          included the number of cigarettes smoked, alcohol intake,
technical/biomed/1478-7954-1-3.txt:          of cigarettes smoked per day calculated for smokers;
technical/biomed/1478-7954-1-3.txt:          there was a decline over time in the cigarettes smoked.
technical/biomed/1478-7954-1-3.txt:          associated with weight, whereas cigarettes smoked were
technical/biomed/1478-7954-1-3.txt:          of cigarettes smoked was negatively associated with HDL.
technical/biomed/1478-7954-1-3.txt:          LDL. However, the number of cigarettes smoked was
technical/biomed/1478-7954-1-3.txt:          LDL and HDL concentrations, cigarettes smoked, and
technical/biomed/1478-7954-1-3.txt:        alcohol consumption, and cigarettes smoked. An advantage of
technical/biomed/1478-7954-1-3.txt:        Third, the effects of smoking 14 cigarettes per day at
technical/biomed/1478-7954-1-3.txt:        halving the average number of cigarettes smoked would
technical/biomed/bcr583.txt:        carcinogenic exposures. Among atomic bomb survivors and
technical/biomed/bcr605.txt:            controls had ever smoked cigarettes (59% and 55%,
technical/biomed/rr172.txt:          Kentucky standard cigarettes (1R3F; University of
technical/biomed/rr37.txt:          substantial proportion reported ever smoking cigarettes

```

grep -e cigarettes -e carcinogenic technical/biomed/*

The -e option allows you to grep for multiple strings at once. For the example above, I grepped the biomed directory for files containing cigarettes or carcinogenic.
