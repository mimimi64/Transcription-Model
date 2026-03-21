This model has everything the first model has and more. It deals with the speaker drift from noisy chatter - mislabelling of speakers due to other background human voice frequencies being added to foreground speakers' blueprints and distorting the embedding - by splitting up audio into much smaller chunks and diarising / transcribing using the speaker map provided by the user, and labelling using global blueprints. Currently the chunks are 3 minutes long, but one can change this. It still adheres to the chronological order of appearance given by the user however, and will attempt to create new global ID's for speakers it doesnt recognise match with already established blueprints, past a certain threshold of recognition from 0 to 1, again which is changeable.





