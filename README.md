# Gelbooru widescreen wallpapers downloader


Download various widescreen anime pictures from Danbooru from your chosen character/anime tag.

Now you'd be asking, why not just search with ratio:16:9? Yes that's if you want exactly that aspect ratio, but as artists do, they just post in a huge variety of specific aspect ratios. 

And since there's no way to search between a variety of aspect ratios natively in Danbooru, this will download search results from aspect ratios ranging from 3:1 (super ultrawide) to 4:3.

https://github.com/user-attachments/assets/24ae5276-049c-4aac-9690-43a3da5ffa7d

# Requirements:

- Python 3.7+
- requests
- beautifulsoup4

Tested in Windows 10.

### Install via CMD:

> pip install requests beautifulsoup4

### To use:

Just download the release and extract in a subfolder.

Then just run 'danbooruratiodl_run.bat' or run the .py itself manually in CMD.

You'll be prompted first for the character/anime tag, then if you want NSFW results with yes/no.

# How and what the program does:

This is done by using a large factor number like 128:x to search through a multitude of aspect ratios, whereas x = the second value. So for example, 128:72 is 16:9 and 128:96 is 4:3. This in theory should do the majority of widescreen aspect ratios as it rounds off from such a big factor. Maybe it'll miss 1 out of 200 results, else you can increase the factor to go into greater amounts.

You can shorten or enlarge the aspect ratios to search in "for x in range(42, 97):" with your desired range.

By default it'll skip video/animated filetypes in "return any(filename.lower().endswith(ext) for ext in [".mp4", ".webm", ".swf", ".gif", ".zip"]". Remove or append the filetypes as you like. Now it would be nice to append by default -animated to the search result or add more character tags, but unfortunately it goes over the 2 tag limit for us free plebeians :/

Filename format goes as for example "ratio128x67_5941842..." with the first being ratio, second being the post ID number, then the posts tag etc.

Search duration/API fetch speed reflects the typical value of free users.

## Other remarks

Choose Danbooru for this script as Gelbooru, Sankaku Complex, Konachan and the likes have no aspect ratio search feature. They either have order:landscape that's arbitrary and/or a pixel width/height search function.

This script was done using perplexity ai as I'm a very novice programmer, but from my testing it definitely works and goes through all page results to not miss anything.
