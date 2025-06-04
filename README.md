# Download-Vimeo-Videos

## Overview
This Python script extracts information about your Vimeo videos and organizes their download links, allowing you to back up your own content efficiently.

## Requirements
Make sure you have the following dependencies installed:
- `IPython`
- `pprint`

from dic import dicionario_vimeo
import pprint
from IPython.display import display

# Extracts the list of videos from the dictionary
informations = dicionario_vimeo['data']
videos = []  # List to store organized video data

for item in informations:
    video_uri = item['uri']
    video_name = item['name']
    video_duration = item['duration']
        
    link_540p = ''
    link_720p = ''
    link_1080p = ''
    
    # Extracts the list of download links
    list_downloads = item['download']
    for dictionary_download in list_downloads:
        if dictionary_download['rendition'] == '540p':
            link_540p = dictionary_download['link']
        if dictionary_download['rendition'] == '720p':
            link_720p = dictionary_download['link']
        if dictionary_download['rendition'] == '1080p':
            link_1080p = dictionary_download['link']
            
    dic_item = {
        'uri': video_uri,
        'name': video_name,
        'duration': video_duration,
        'link540p': link_540p,
        'link720p': link_720p,
        'link1080p': link_1080p
    }
    
    videos.append(dic_item)  # Adds the video dictionary to the list

# Displays the organized video list
display(videos)
# Backup Your Own Vimeo Videos Using Python

## Overview
This Python script extracts information about your Vimeo videos and organizes their download links, allowing you to back up your own content efficiently.

## Picture
![Backup Illustration](your-image-link-here)

## Requirements
Make sure you have the following dependencies installed:
- `IPython`
- `pprint`

You can install missing dependencies using:
```bash
pip install ipython


