# collabtogdrive
# Meta-Llama-3-8B Model

This repository provides instructions for directly downloading the Meta-Llama-3-8B language model for text generation to your Google Drive.
To directly download the Meta-Llama-3-8B language model to your Google Drive, follow the steps in the code snippet provided in the 'Downloading and Saving the Model' section of this README.


## Initial Setup

### 1. Hugging Face Token

To get started, you will need an API token from Hugging Face, which will allow you to download pre-trained models. Follow the steps below to create your token:

- Log in to your account on [Hugging Face](https://huggingface.co/).
- Go to the [Settings](https://huggingface.co/settings/tokens) section of your account.
- Click on "New token".
- Name your token and select the appropriate scope (e.g., `read`).
- Click on "Create a token".
- Securely store the generated token.

### 2. Adding the Secret Key in Google Collab

To add your secret key (which contains the Hugging Face token) in Google Collab, follow these steps:

- Open your notebook in Google Collab.
- On the left side, there is an icon that looks like a lock. Click on it to open the 'Secrets' section.
- Click on “Add new secret”.
- In the name field, type `HF_TOKEN` without spaces.
- Paste the value of your Hugging Face token into the value field.
- Click "Add" to save the secret.

## Downloading and Saving the Model

To download and save the model to your Google Drive, execute the following code in Google Collab:

```python
import torch
from transformers import AutoModelForCausalLM
from google.colab import drive, userdata
import os

# Set the HF_TOKEN secret in the Colab secrets
hf_token = userdata.get('HF_TOKEN')

# Create a directory named "llama3" in the Google Drive
os.makedirs('/content/drive/MyDrive/llama3', exist_ok=True)

# Load the model
model_id = "meta-llama/Meta-Llama-3-8B"
model = AutoModelForCausalLM.from_pretrained(model_id, token=hf_token)

# Save the model to the "llama3" folder in Google Drive
with open('/content/drive/MyDrive/llama3/Meta-Llama-3-8B.pth', 'wb') as f:
    torch.save(model.state_dict(), f)

print('Model successfully loaded!')


