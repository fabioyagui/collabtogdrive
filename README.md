# collabtogdrive
Initial Setup
1. Hugging Face Token
To get started, you'll need a Hugging Face API token that allows you to download pre-trained models. Follow the steps below to create your token:

Log in to your account on Hugging Face.
Go to the Settings section of your account.
Click on "New token".
Name your token and select the correct scope (e.g., read).
Click on "Create a token".
Securely store the generated token.
2. Adding the Secret Key in Google Colab
To add your secret key (which contains the Hugging Face token) in Google Colab, follow these steps:

Open your notebook in Google Colab.
Go to the Runtime > Change runtime type menu and ensure you are using a GPU runtime environment if necessary.
In the notebook, access the Runtime > Add secret menu.
In the window that appears, enter the key HF_TOKEN and paste the value of your Hugging Face token.
Click on "Add" to save the secret key.
