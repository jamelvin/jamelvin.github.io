---
title: "One-Way Classification of Composer of Classical Music Pieces using Support Vector Machines"
excerpt_separator: "<!--more-->"
categories:
  - Project
tags:
  - Support Vector Machines
  - One-Way Classification
  - Audio Files
---

The [MusicNet database](https://arxiv.org/pdf/1611.09827.pdf) is an annotated set of hundreds of classical music pieces in Midi file format.  The task is given a subset of the database with the majority of the pieces categorized into 4 composers (Beethoven, Bach, Brahms and Schubert) and the rest uncategorized (only 3 do not belong to the 4 specified composers), build a model to determine which uncategorized files were NOT composed by the 4 composers that partitioned the known data.  
 
<!--more-->

This is a binary classification problem, but our annotated data only has positive cases.  One-Class Support Vector Machine (SVM) provides a useful approach to this type of classification problem and is the one pursued here.  Before building a model, a python interpreter to interact with the provided MIDI files is needed.

I chose to mainly use [Pretty_Midi](https://craffel.github.io/pretty-midi/) for this purpose, providing a quick, easy-to-use library to extract relevant features of the music files.  Since only the raw annotated music files were provided, musical theory can help us develop some ways to parse the data that may be relevant to determining the composer.  For this initial approach, I extracted the following information:

- Number of Each Instrument,
- Dissonance,
- Frequency of Piano Chords and Intervals,
- Range of Pitches,
- Duration of Piece.

Using this data, a One-Class SVM was built and tuned on the annotated data and then tested on the unannotated set.  With the fully tuned SVM model, 5 of the uncategorized files were identified as not belonging to the 4 composers, of which there were only 3 out of 35 that were not by the 4 composers.

For the detailed analysis, discussion and Python code, see the repository [here](https://github.com/jamelvin/MusicNet-SVM).
