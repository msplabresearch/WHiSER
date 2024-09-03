
The Annotation folder includes:
	- readme.txt (this file)
	- Folder Annotation_wav_files.zip (it contains the audio files which are annotated (total 5427 files))
	- Labels/
	        - labels.txt (raw file with emotional annotation information) 
                - labels_consensus.csv (aggregated annotations in CSV format)
	        - labels_detailed.csv (detailed individual annotations in CSV format)
	        - labels_consensus.json (aggregated annotations in JSON format)
	        - labels_detailed.json (detailed individual annotations in JSON format)
	- Annotation_wav_files_ref.txt (This file shows the source of selected annotation file (Annotation_file_name source_file_name start_time    duration))
	

************************************
    Emotional Labels 
************************************

The emotional labels are in the folder "Labels". The main file is labels.txt, which contains all the emotional evaluations collected for this set. The format of this file is explained below. In addition, we include the emotional labels and meta-information in CSV and JSON format:

CSV format: 	[labels_consensus.csv, 	labels_detailed.csv]
JSON format: 	[labels_consensus.json, labels_detailed.json]

labels_consensus => include: emotion labels after aggregating the annotations (primary emotion, secondary emotions, emotional attributes), gender, speaker and split set information.
labels_detailed => individual annotation provided by each worker to each sentence 


The database label file (labels.txt) is organized as follows:

The annotations of each audio file are shown together with an empty line separating the annotations of different files. This is an example of one file:

006-040.1-2_13.wav; H; A:4.200000; V:4.800000; D:5.000000;
WORKER00014325; Sad; Sad,Concerned; A:2.000000; V:4.000000; D:4.000000;
WORKER00014332; Happy; Happy,Concerned; A:4.000000; V:6.000000; D:6.000000;
WORKER00014342; Fear; Neutral,Concerned,Fear; A:5.000000; V:3.000000; D:5.000000;
WORKER00014343; Happy; Happy,Concerned; A:5.000000; V:5.000000; D:5.000000;
WORKER00014344; Happy; Happy; A:5.000000; V:6.000000; D:5.000000;

[next file] ...

Explanation about the annotation:
We are collecting three set of information:

1-) Arousal, valence and dominance
	- we use Self-Assessment Manikin (SAM) where rankings go from 1 to 7
	- valence (1-very negative; 7-very positive)
	- arousal (1-very calm; 7-very active)
	- dominance (1-very weak; 7-very strong)

2-) primary emotions (categorical)
	- only one option is allowed
	- you can say "other" and define your own emotional class

Primary emotions and the consensus emotion code:
Angry		(A)
Sad		(S)
Happy		(H)
Surprise	(U)
Fear		(F)
Disgust		(D)
Contempt	(C)
Neutral		(N)
Other		(O)
No agreement    (X)	//when there is no plurality voting winner between the above emotions


3-) secondary emotions
	- you can select as many emotional classes as you want
	- you can also select "other" and specify the emotional class

Secondary emotions:

Angry
Sad
Happy
Amused
Neutral
Frustrated
Depressed
Surprise
Concerned
Disgust
Disappointed
Excited
Confused
Annoyed
Fear
Contempt
Other

Few explanations about this format:
1)- the first line brings a summary of the sentence. First, it provides the name of the segment (in this case 006-040.1-2_13.wav). Then it provides the consensus (plurality vote) of primary emotion (in this case "N" for Neutral since 3 our of 5 people selected this option). Then, it provides the average values for A: activation (2.4), V:valence (4.0) and D:dominance (2.8)

2)- The next lines provide individual evaluations from evaluators
	a) first, it is the ID that we assigned to workers (e.g., WORKER00014325 for the first evaluator).
	b) Then, it lists the primary emotion ('Other-confused'). They can choose from Angry, Sad, Happy, Surprise, Fear, Disgust, Contempt, Neutral and Other. In the first case they chose Other, and then they suggested the label "confused"
	c) Then, it lists the secondary emotion ('Concerned,Confused'). They can choose from the following list: Angry, Sad, Happy, Amused, Neutral, Frustrated, Depressed, Surprise, Concerned, Disgust, Disappointed, Excited, Confused, Annoyed, Fear, Contempt, Other. A key difference here is that they can choose multiple options as oppose to primary emotions where they can only select one. 
	d) The values for arousal, valence and dominance (A:3.000000; V:3.000000; D:4.000000;)

