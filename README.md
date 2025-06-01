🌟 LoRA Easy Training Colab - Dataset Preparation & Training
This guide helps you set up and train LoRA models using HuggingFace datasets and the LoRA Easy Training Colab. Follow these steps to gather data, auto-tag images, and start training.

🗂️ 1. Dataset Download and Extraction
Upload or paste a .zip file link of your dataset from HuggingFace.

Set zip_path:

python
Copy
Edit
zip_path = "/content/drive/MyDrive/dataset.zip"
extract_to_dataset_dir = "dataset"
hf_token = ""  # Required only if private repo
If your zip link is from HuggingFace, make sure it ends with .zip and follows the format:

ruby
Copy
Edit
https://huggingface.co/username/repo/resolve/main/dataset.zip
The script will:

Download the .zip file

Extract it into the dataset folder

Clean up the temporary zip

🏷️ 2. Auto-Tagging Images
Set your tagging preferences:

python
Copy
Edit
method = "Anime"  # or "Photorealistic"
model = "SmilingWolf/wd-eva02-large-tagger-v3"
dataset_dir_name = "dataset"
file_extension = ".txt"
blacklisted_tags = ""
threshold = 0.25
caption_min = 10  # only used for photorealistic
caption_max = 75
Anime: Uses pretrained taggers for style tags.

Photorealistic: Uses caption generation.

Then run caption_images() to tag all images.

🏁 3. Start Training
Run print_paths() to get the following:

Dataset path

Model path

VAE path

Output path

These paths are used in the UI or terminal to configure training.

🔗 4. Local UI Tunnel (Optional)
If using local UI to control training:

Install UI tool from the official repo

Launch your local UI

Enter the training URL shown in Colab

Send training parameters and start

✅ Requirements
Google Drive mounted

HuggingFace Access Token (if dataset is private)

Recommended: GPU backend

