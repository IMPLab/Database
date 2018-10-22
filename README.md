# Introduction
Reading is an activity we perform every day to entertain ourselves, to stay informed and to acquire knowledge. The content we read and the way we read it can tell a lot about ourselves. Therefore, researchers have studied our reading behaviors for decades. 

Especially, they have used eye trackers system to record and analyze our eye movements while reading. From the way he moves his eyes, it is now possible to quantify the reader’s understanding, emotions or interest. Nowadays, researchers want to extract even more information  about the reader by analyzing his reading behavior. To do so, it might be necessary to use cutting edge machine learning techniques such as deep learning. Deep learning has enabled outstanding results in various domains such as language processing, image recognition, etc. However, all the successful methods using such algorithms have one similarity: they need  huge datasets to perform well (ten thousands of pictures, hours of videos, millions of sentences, etc.).
The neural networks need to see a lot of different examples in order to be able to generalize well.

In the context of eye tracking research, and particularly for reading behavior analysis, it is a strong limitation for several reasons:
	- The eye tracking technology is not common enough so that we can ask thousands of people to use it.
	- It is difficult to record a participant reading for hours in order to get enough data.
	- The webcam based eye tracking methods are not developed enough to be used for reading behavior analysis.

Therefore, we need to foster the development of large datasets where people are recorded by an eye tracker while reading.
Few databases are publicly available:

###### The Provo Corpus
In this database, 84 participants were asked to read 55 texts from various sources such as news articles, science magazines and public domain fictions.
The passages were on average 50 words long and contained 2.5 sentences on average (each sentence was 13.3 words long on average).
Across all the texts, there were 2689 words.
The eye movements were tracked by a professional eye tracker sampling at 1000 Hz.
The eye tracking data is [publicly available](https://osf.io/sjefs/).
For each participant and each word of the text, different information is available: how many fixations on this word, how many time this word is included in a regression, etc.
However, the raw eye gaze is not available.

###### The GECO corpus
In this database 19 Dutch-English bilingual and fourteen English monolingual students were asked to read an entire novel.
The eye movements were tracked by a professional eye tracker sampling at 1000 Hz.
The eye tracking data is [publicly available](http://expsy.ugent.be/downloads/geco/).
Similarly to the Provo corpus, some information is available for each word, the raw eye gaze is not available.


###### The Dundee Corpus
In this corpus, 10 native English speakers and 10 French speakers read newspapers editorials.
Each text contained about 50 000 words.
This corpus is available on demand.


All these corpus had a strong impact on the reading behavior research because they gathered dozens of participants reading very long texts. However, they suffer from several drawbacks: the raw eye gaze data is not included, and they use only professional devices which are unlikely to be used in an everyday life environment. Here, we present our own database, the IMLAB database, which is meant to be a contribution to sharing of eye tracking database.
The details are given below:

# The IMLAB database
The database corresponds to the experiment presented in the paper [Wordometer systems for everyday life](https://dl.acm.org/citation.cfm?doid=3178157.3161601). In this experiment 14 non-native English speakers from various nationalities were asked to read English texts. Their eye movements were recorded by several sensors:  Tobii Eye X, JINS MEME, Pupil, SMI RED250, SMI mobile eye tracker. All the texts were extracted from the website Newsela. That website provides news with different grades of English difficulty.
The readers were asked to follow the experimenter instructions regarding the way of reading the texts.
Three scenarios could occur:
- The reader was asked to read the text carefully, without rereading nor skipping.
- The reader was asked to skip a part of the text (decided beforehand).
- The reader was asked to reread a part of the text (decided beforehand).



###### Metadata.txt
More details are provided in the file: “metadata.txt”.
The content of this file is described here:


Label | Meaning
----- | -------
**Text** | the name of the text.
**Author** | the journal from where the text was originally published.
**Adaptation** | who modified the text to adapt its difficulty to different grade level.
**Grade level** | difficulty of the texts (by school grade).
**Word count** | the number of words.
**Lexile** | difficulty of the text [(Newsela Lexile scale)](https://support.newsela.com/hc/en-us/articles/360008500391-Grade-to-Lexile-Conversion).
**Link** | url of the text.
**Scenario** | *None* (no rereading, no skipping), *Rereading*, *Skipping*, *Layout* (the layout of the text is different), *SideExp* (equivalent to “None”).
**Read Word Count** | number of words read by the reader (Greater in the Rereading scenario, Less in the Skipping scenario compared to “Word Count”).

###### Files organization
The first folder (eg: 08.11) corresponds to the day of recording.
The next folder is the participant number (all files have been anonymised).
In the folder of each participant is included the device used to record the participant eye movements (one folder for each device).
In each of the device-folder is included the raw recording of the eye gaze (csv format), a log file (start and end time, date), and the png file of the read texts.
The csv file is named following the notation “nameOfText_device.csv” where "nameOfText" is the name of the text as described in metadata.txt and "device" is the deviced used.
The details of each csv file can be retrieved in the corresponding device manufacturer website.



