# Fine-Grained Controllable Emotion Text Generation through Prompt Tuning
## Description
Performs prompt tuning on corpora extracted from the GoEmotions dataset, to train soft prompts usable for Controllable Text Generation for various emotions. In other words, we provide an approach to guide a language AI model towards generating text of a certain emotionality. 

Soft prompts have the benefit of being very light-weight when it comes to inference cost and store space, and GoEmotions provides a wide variety of emotions to train on.

Please contact me for access to the full report.

### Evaluation
A human survey was performed to evaluate the performance of trained soft prompts, for **emotional consistency** and **grammatical correctness**. Statistical tests are then performed. We include here only the aggregate results: 

- For **emotional consistency**, 4 out of 6 emotion soft prompts rejected the null hypothesis for the Chi-square tests of independence (w/ 95% CI) and the increase in average accuracy over all soft prompts is **+164.925%** when compared to the baseline model. 

- For **grammatical correctness**, 5 out of 6 rejected the null hypothesis for the Student's t-tests (w/ 95% CI) with an average accuracy decrease of **-12.947%** against the base model.

As for size, each soft prompt takes up **67 KB** of disk storage and **20 tokens** in the model's context.

## How to Use
3 jupyter notebooks are available: to preprocess the GoEmotions dataset, to train and use the soft prompts, and the notebook used for survey evaluation.

The dataset pre-processing notebook isnt required, the corpora folder contains the dataset alredy preprocessed for certain emotions. The survey evaluation notebook is there for posterity but the survey answers themselves are not included.

See **Structure** section for where to find everything. 

## Limitations
The GoEmotions dataset has flaws for this purpose. It being composed of social media comment adds bias to soft prompts that limits its consistency in other contexts than generating social media comments. For example, the prevalance of slang like "lol", emojis and lowered grammatical correctness. 

Soft prompts have limited controllability; a lack of an emotion intensity parameter. Given the CTG field moves fast, new approaches get developed quickly and many of them could be considered. For example, adapters.

## Structure
**dataset/** : Contains the GoEmotions dataset, divided into 3 csv files.

**preprocess_dataset/** : Contains the jupyter notebook (and requirements) for preprocessing the GoEmotions dataset for training.

**preprocess_dataset/corpora/** : Contains each prepared emotion corpus to use for prompt tuning.

**prompt_tuning/** : Contains the jupyter notebook (and requirements) for the prompt tuning and inference process.

**survey/** : Contains the survey's text snippets, and the notebook (and requirements) for Prolific answer analysis. Note, the answers to perform the analysis are not included here.
