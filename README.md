# Alfred Clipboard Teleporter
<img src="https://user-images.githubusercontent.com/1700689/120085243-4412c500-c08b-11eb-9cea-7d973894c38e.jpg" width=700>
An Alfred workflow to copy the most recent image from Alfred clipboard into a folder hosted by a local webserver. 
> This workflow is particular to one of my daily routines. You might want to evolve this workflow to your custom needs or reuse parts of it to automate your daily life!

## Pre-requisites
1. Install https://www.alfredapp.com/
1. Enable [Alfred workflows](https://www.alfredapp.com/workflows/)
1. Enable clipboard history for Images on Alfred <img src="https://user-images.githubusercontent.com/1700689/120085326-10846a80-c08c-11eb-93dc-98ce8a9688db.png" width = 500>
1. OPTIONAL - Install [Web Server for Chrome](https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb?utm_source=chrome-ntp-launcher). You will copy the image from the clipboard to a folder managed by this webserver
## Some more setup instructions
>  👇️ Following steps should be run after the workflow is installed
1. Install [Pillow](https://python-pillow.org/) module for **Python 2.7**. This takes care of converting \*.tiff file to \*.jpeg
    > Alfred currently works with Python 2.7 only. So, I installed the Python module using in the following way and into the workflow folder
    1. Once the workflow is created, navigate to the workflow folder in Finder
    1. Use the script `python2 -m pip install --target=. Pillow` to install the package
    1. Once installed, the folder structure would look like <img src="https://user-images.githubusercontent.com/1700689/120085484-60affc80-c08d-11eb-8732-9e9d4256d0a0.png" width=300>
1. Set up the followig environment variables <img src="https://user-images.githubusercontent.com/1700689/120085523-c00e0c80-c08d-11eb-8623-fe77801dd5bc.png" width=400>
    1. `db_name` should be `clipboard.alfdb`
    2. `db_path` should be `Library/Application Support/Alfred/Databases`
    3. `dest_dir` should be the target folder to place your image

## Running the Workflow
1. I have the workflow set up to be triggered on receiving `\\pi` keystroke or a hotkey
2. When the workflow is triggered, it will copy the most recent image from Alfred's clipboard and copy it to the `dest_dir`
![](https://user-images.githubusercontent.com/1700689/120085798-08c6c500-c090-11eb-96d0-7e598a30918b.gif)


