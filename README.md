# Gelbooru widescreen wallpapers downloader
![Gelbooru widescreen wallpaper downloader - Full logo (2560)](https://github.com/user-attachments/assets/020801f8-7c3f-44b6-8b0e-93a45d06670c)

Download various widescreen anime pictures from Gelbooru from your chosen character/anime tags.

Since there's no way to search between a variety of aspect ratios natively in Gelbooru, this will download search results from aspect ratios ranging from 3:1 (super ultrawide) to 4:3.

### [Check out the Danbooru version too.](https://github.com/acoolrocket/Danbooru-widescreen-wallpapers-downloader)

https://github.com/user-attachments/assets/ea97109c-77a9-4181-881c-57fc945fa24e

# Requirements:

- Python 3.7+
- requests
- beautifulsoup4
- pillow

Tested in Windows 10.

### Install via CMD:

> pip install requests beautifulsoup4 pillow

### To use:

Just download the release and extract in a subfolder.

Then just run 'gelbooruratiodl_run.bat' or run the .py itself manually in CMD.

You'll be prompted first for the character/anime tags, then if you want NSFW results with yes/no and animated content.

# How and what the program does:

This program goes through each page and fetches all thumbnail's resolution to decide if the aspect ratio qualifies for a 4:3 at least.

For example 350x350 would mean a 1:1 aspect ratio and fail, but 350x233 qualifies as a wider than 4:3 aspect ratio. 

You can change the minimum aspect ratio from line 14:

    def aspect_ok(width, height):
        return (width / height) >= (4 / 3)

Whereas 4:3 is the default.

It will very likely go through all pages of your chosen tags due to Gelbooru's very lenient API calls limit. I've been able to fetch 3k-4k images going through hundreds of pages.

## Other remarks

This script was done using perplexity ai as I'm a very novice programmer, but from my testing it definitely works and goes through all page results to not miss anything.

I've made this in tandem with a Danbooru version whereas if you're a collector I'd recommend utilizing both scripts since some posts can be exclusively on either Gelbooru or Danbooru and you can combine the resulting downloads of both pulls together, delete duplicates with a file organizer like [Czkawka](https://github.com/qarmin/czkawka) with an exact file size matcher and duplicate image detector especially useful for multi-variant artworks.
