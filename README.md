# EvalYaks


### _EvalYaks_: Instruction Tuning Datasets and LoRA Fine-tuned Models for Automated Scoring of CEFR B2 Speaking Assessment Transcripts

Relying on human experts to evaluate CEFR speaking assessments in an e-learning environment creates scalability challenges, as it limits how quickly and widely assessments can be conducted. We aim to automate the evaluation of CEFR B2 English speaking assessments in e-learning environments from conversation transcripts. First, we evaluate the capability of leading open source and commercial Large Language Models (LLMs) to score a candidate's performance across various criteria in the CEFR B2 speaking exam in both global and India-specific contexts. Next, we create a new expert-validated, CEFR-aligned synthetic conversational dataset with transcripts that are rated at different assessment scores. In addition, new instruction-tuned datasets are developed from the English Vocabulary Profile (up to CEFR B2 level) and the CEFR-SP WikiAuto datasets. Finally, using these new datasets, we perform parameter efficient instruction tuning of Mistral Instruct 7B v0.2 to develop a family of models called _EvalYaks_. Four models in this family are for assessing the four sections of the CEFR B2 speaking exam, one for identifying the CEFR level of vocabulary and generating level-specific vocabulary, and another for detecting the CEFR level of text and generating level-specific text. _EvalYaks_ achieved an average acceptable accuracy of 96\%, a degree of variation of 0.35 levels, and performed 3 times better than the next best model. This demonstrates that a 7B parameter LLM instruction tuned with high-quality CEFR-aligned assessment data can effectively evaluate and score CEFR B2 English speaking assessments, offering a promising solution for scalable, automated language proficiency evaluation.



```plaintext
EvalYaks/
├── Files
│   ├── AverageAcceptableAccuracy_PerformanceDescriptors.png
│   ├── AverageAcceptableAccuracy_WithoutPerformanceDescriptors.png         
│   ├── DatasetExample.png                                            
├── InstructionDatasets/                        # Datasets used for instruction tuning
│   ├── Cambridge_VocabProfile.csv              # Cambridge Vocabulary Profile
│   ├── CEFR_WikiAuto.csv                       # CEFR WikiAuto Dataset
│   ├── Part1_Introduction.csv                  # Part 1 of CEFR B2 English speaking assessment
│   ├── Part2_LongTurn.csv                      # Part 2 of CEFR B2 English speaking assessment
│   ├── Part3_Discussion.csv                    # Part 3 of CEFR B2 English speaking assessment
│   ├── Part4_ExtendedDiscussion.csv            # Part 4 of CEFR B2 English speaking assessment
├── LICENSE                                                       
└── README.md     
```

### Datapoint examples for different parts of the speaking assessment for instruction tuning.
![Datapoint examples for different parts of the speaking assessment for instruction tuning.](InstructionDatasets/DatasetExample.png)

### The distribution of acceptable accuracy of leading LLMs without LoRA in comparison with \textit{EvalYaks} part 1-4 models using prompts without performance descriptors.
![The distribution of acceptable accuracy of leading LLMs without LoRA in comparison with \textit{EvalYaks} part 1-4 models using prompts without performance descriptors.](InstructionDatasets/AverageAcceptableAccuracy_WithoutPerformanceDescriptors.png)

### The distribution of acceptable accuracy of leading LLMs without LoRA in comparison with \textit{EvalYaks} part 1-4 models using prompts with performance descriptors.
![The distribution of acceptable accuracy of leading LLMs without LoRA in comparison with \textit{EvalYaks} part 1-4 models using prompts with performance descriptors.](InstructionDatasets/AverageAcceptableAccuracy_PerformanceDescriptors.png)
