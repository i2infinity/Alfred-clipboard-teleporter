# Alfred Clipboard Teleporter
![393165e56a9133ecd3dc68c47a5a2c8d5141f8bf](https://user-images.githubusercontent.com/1700689/120085243-4412c500-c08b-11eb-9cea-7d973894c38e.jpg)
An Alfred workflow to copy the most recent image from Alfred clipboard into a folder hosted by a local web server. 
> This workflow is highly specific to one of my daily routines. You might want to evolve this workflow to your custom needs or reuse parts of it to automate your daily life!

## Pre-requisites
1. Install https://www.alfredapp.com/
1. Enable [Alfred workflows](https://www.alfredapp.com/workflows/)
1. Enable clipboard history for Images on Alfred ![image](https://user-images.githubusercontent.com/1700689/120085326-10846a80-c08c-11eb-93dc-98ce8a9688db.png)
1. OPTIONAL - Install [Web Server for Chrome](https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb?utm_source=chrome-ntp-launcher). You will copy the image from the clipboard to a folder managed by this web server
## Some more setup instructions
>  👇️ Following steps should be run after the workflow is installed
1. Install [Pillow](https://python-pillow.org/) module for **Python 2.7**. This takes care of converting \*.tiff file to \*.jpeg
    > Alfred currently works with Python 2.7 only. So, I installed the Python module using in the following way and into the workflow folder
    1. Once the workflow is created, navigate to the workflow folder in Finder
    1. Use the script `python2 -m pip install --target=. Pillow` to install the package
    1. Once installed, the folder structure would look like ![image](https://user-images.githubusercontent.com/1700689/120085484-60affc80-c08d-11eb-8732-9e9d4256d0a0.png)
1. Set up the followig environment variables ![image](https://user-images.githubusercontent.com/1700689/120085523-c00e0c80-c08d-11eb-8623-fe77801dd5bc.png)
    1. `db_name` should be `clipboard.alfdb`
    2. `db_path` should be `Library/Application Support/Alfred/Databases`
    3. `dest_dir` should be the target folder to place your image

## Running the Workflow
1. I have the workflow setup to be triggered on receiving `\\pi` keystroke or a hotkey
2. When the workflow is trigerred, it will copy the most recent image from Alfred's clipboard and copy it to the `dest_dir`


