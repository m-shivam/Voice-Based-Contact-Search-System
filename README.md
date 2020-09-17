## Voice-Based-Contact-Search-System
### HMM based speech model to search names with user

Source Contributors
MAYANK SHARMA,
SHIVAM MAURYA,
RUPAK GUPTA

The project is about voice based search of the contact names and details in the list. The main idea of the project is to take an input in the form of speech and outputs the name spoken onto the screen. We have used various concepts like cepstral coefficients, Durbin’s algorithm, Viterbi algorithm, LBG algorithm, HMM procedures, etc. There are 15 words in our list that makes total of 15 models.

The basic flow of the project goes this way:
First, the input signal is recorded, processed (DC shift, normalization, etc.) and then we get ci’s out of signal frames. Once we get ci’s, using codebook generated by LBG algorithm, we get an observation sequence corresponding to an input. In training, we start with the inertia model and convert it into a trained model using Forward Backward, Viterbi algorithm and Re-estimation procedure. While in testing, we use forward procedure to get the maximum probability of the model using a specific observation sequence.
\newline
It has 4 basic functions namely;
    • Training: This module uses some pre-recorded input files to train the models of each name in the contact list. It stores such models in files. Also, for better testing accuracy, we have run the training module thrice instead of just once, thus we get 3 models for each word that makes total of 45 models.

    • Pre-recorded Testing: The testing module uses HMM Forward procedure to calculate the maximum probability of a particular observation sequence and outputs the best match one.
In prerecorded testing, some files are given as input in a loop and it returns accuracy of the testing.

    • LIVE Training: The models have been trained by a single user, thus when tested by some other user, the accuracy will no more be better. Thus, for the scalability purpose, we have added a LIVE training module in which a user is supposed to select a word to be trained and record 10 utterances of that word. After this, the model gets updated and will return a relatively better accuracy when tested by this new user.

    • LIVE Testing: The testing module uses HMM Forward procedure to calculate the maximum probability of a particular observation sequence and outputs the best match one.
In LIVE testing, the user speaks a name and gets it printed on the screen.
