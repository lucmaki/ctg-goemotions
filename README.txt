# Fine-Grained Controllable Emotion Text Generation through Prompt Tuning
## Description
Performs prompt tuning on corpora extracted from the GoEmotions dataset, to train soft prompts usable for Controllable Text Generation for various emotions.
Soft prompts have the benefit of being very light-weight when it comes to inference cost and store space, and GoEmotions provides a wide variety of emotions to train on.

## Limitations
The GoEmotions dataset has limitations. It being composed of social media comment adds bias to soft prompts that make inpractical for other contexts than generating social media comments. 
Soft prompts have limited controllability; a lack of an emotion intensity parameter. The CTG field moves fast, new approaches get developed quickly, many of them could be considered.

## Structure
*dataset/* : Contains the GoEmotions dataset, divided into 3 csv files.
*preprocess_dataset/* : Contains the jupyter notebook (and requirements) for preprocessing the GoEmotions dataset for training.
*preprocess_dataset/corpora/* : Contains each prepared emotion corpus to use for prompt tuning.
*prompt_tuning/* : Contains the jupyter notebook (and requirements) for the prompt tuning and inference process.
