# bad-cv-clips
Ongoing project to identify "bad" clips in Common Voice dataset releases. PRs with new clip filenames are welcomed.

[transcript_check.py](https://github.com/dabinat/deepspeech-tools/blob/master/transcript_check.py) was used to flag up potential problem clips, which were then manually validated. While transcript_check.py is intended to flag up clips significantly shorter/longer than their expected transcript, additional problem clips were found along the way. The CSV therefore also contains robotic/filtered voices, recordings too quiet, incorrect transcripts, truncated recordings, clipped audio, repetitions and noise drowning out words.

The CSV contains the original expected transcript to make it easy for others to double-check any clip.

You can use [csv_purge.py](https://github.com/dabinat/deepspeech-tools/blob/master/csv_purge.py) to strip these files from the DeepSpeech CSVs. The bad clip CSV contains results from dev, train and test combined, so you should run it once on each segment to make sure everything gets removed.

Removing these clips then training the 0.5.1 checkpoint with the CommonVoice data improved WER from 0.488 to 0.465.
