# GenAICourse
# This repo is for me to upload my GenAI course works


Assignment reject due to the followings:
Dear Student

We need to train a sequence Classification model and not a Causal LM .

While I find the steps to be almost correct, I feel changing to Sequence Classification would make the project complete.

Also you should compare the pre trained hugging model post loading directly and not use trainer.train() on pre trained model.

#Revisit criteria

Prepare the Foundation Model
Criteria	Submission Requirements

Load a pretrained HF model
	

Includes the relevant imports and loads a pretrained Hugging Face model that can be used for sequence classification

Load and preprocess a dataset
	

Includes the relevant imports and loads a Hugging Face dataset that can be used for sequence classification. Then includes relevant imports and loads a Hugging Face tokenizer that can be used to prepare the dataset.

A subset of the full dataset may be used to reduce computational resources needed.

Evaluate the pretrained model
	

At least one classification metric is calculated using the dataset and pretrained model
Perform Lightweight Fine-Tuning
Criteria	Submission Requirements

Create a PEFT model
	

Includes the relevant imports, initializes a Hugging Face PEFT config, and creates a PEFT model using that config

Train the PEFT model
	

The model is trained for at least one epoch using the PEFT model and dataset

Save the PEFT model
	

Fine-tuned parameters are saved to a separate directory. The saved weights directory should be in the same home directory as the notebook file.

