# SD_Auto1111_DreamBooth_and_ControlNet

This is a repo created for preservation purposes. It restores the automatic1111 build to instances where dreambooth has been tested to work with python 3.10 installed on your windows environment.
This was mostly prompted by broken dependencies due to updates in diffusers and transformers library! 

It does contain some tweaks that disable the huggingface safety checker. This is not done to encourage unethical conduct (please don't download this if you intend to do that) but rather because trained dreambooth models would only generate blocked/censored images for some reason (the safety checker would pick up nsfw elements in perfectly sfw images)

### This only works with stable-diffusion 1.5 for now. Do not try to run it on any 2.x model since that functionality is broken as of right now!

## Pre-requisite installs
1. Python 3.10 on windows: https://www.python.org/downloads/release/python-3100/ [tested on: Windows installer (64-bit)]
2. At least a 12 GB VRAM Cuda enabled Graphic Card (if you wish to train dreambooth)

# How to Setup
1. download the repo into your downloads folder
2. <s>Extract the zip file in downloads and select 'skip all' for prompts that tell you that a file cannot be copied.</s>

(IMPORTANT: the python_fixer file has been programmed to only work if the folder is in downloads. It will have to be re-written if you either move the 'booth_tested_stable-diffusion-webui' to some other directory or your default directory for your browser/windows has been changed)

3.  Navigate to 'booth_tested_stable-diffusion-webui' containing all the files (this may vary depending on how you extract the files)
4.  double click/execute/Run python_fixer.bat
5.  Run webui.bat or webui-user.bat and you should be good to go =D

You can use the guide listed here to get started on training your own dreambooth model! 
URL: https://github.com/d8ahazard/sd_dreambooth_extension/wiki/ELI5-Training

<strong>NOTE: </strong>you will need to run the 'dreambooth_output_fixer.bat' file every time you train your own custom dreambooth model to disable the safety checker. This is done because the automatic1111 build given here detects all dreambooth model outputs as nsfw even if they contain no nsfw elements. please do not remove or relocate the 'dreambooth_output_fixer.bat', 'pipeline_stable_diffusion.py' and 'pipeline_stable_diffusion_safe.py' files as this will break the dreambooth_output_fixer.bat code (which means you'll have to manually go in and replace/or code the relevant files every time you're done training a dreambooth model.
