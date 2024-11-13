# GenAICourse
# This repo is for me to upload my GenAI course works


Assignment reject due to the followings:
Dear Student

We need to train a sequence Classification model and not a Causal LM .

While I find the steps to be almost correct, I feel changing to Sequence Classification would make the project complete.

Also you should compare the pre trained hugging model post loading directly and not use trainer.train() on pre trained model.
	# Try the following block:
# Estimate the accuracy of your classifier by comparing your responses to the labels in the dataset

def get_accuracy(response, dataset, original_indices):
    correct = 0
    total = 0

    for entry_number, prediction in response.items():
        if int(entry_number) not in original_indices:
            continue

        label_id = dataset[int(entry_number)]["label"]
        label = id2label[label_id]

        # If the prediction from the LLM matches the label in the dataset
        # we increment the number of correct predictions.
        # (Since LLMs do not always produce the same output, we use the
        # lower case version of the strings for comparison)
        if prediction.lower() == label.lower():
            correct += 1

        # increment the total number of predictions
        total += 1

    try:
        accuracy = correct / total
    except ZeroDivisionError:
        print("No matching results found!")
        return

    return round(accuracy, 2)


print(f"Accuracy: {get_accuracy(response, dataset, range(7, 15))}")




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

