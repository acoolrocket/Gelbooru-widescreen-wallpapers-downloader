# Gelbooru widescreen wallpapers downloader
![Gelbooru widescreen wallpaper downloader - Full logo (2560)](https://github.com/user-attachments/assets/020801f8-7c3f-44b6-8b0e-93a45d06670c)

Download various widescreen anime pictures from Gelbooru from your chosen character/anime tags.

Since there's no way to search between a variety of aspect ratios natively in Gelbooru, this will download search results from aspect ratios ranging from 3:1 (super ultrawide) to 4:3.

### [Check out the Danbooru version too.](https://github.com/acoolrocket/Danbooru-widescreen-wallpapers-downloader)

https://github.com/user-attachments/assets/ea97109c-77a9-4181-881c-57fc945fa24e

# Requirements:

- Python 3.7+
- requests

Tested in Windows 10.

### Install via CMD:

> pip install requests

## To use:

1. Just download the release and extract in a subfolder.

2. Go to account options to fetch the API Access Credentials key at the bottom: https://gelbooru.com/index.php?page=account&s=options

    1. It'll look like &api_key=INSERTAPIKEYTHATSLONGGGG&user_id=000000

    2. Then paste it in "credentials.txt" and save.

3. Then just run 'gelbooruratiodl_run.bat' or run the .py itself manually in CMD.

4. You'll be prompted first for the character/anime tags, then if you want NSFW results with yes/no and animated content.

# How and what the program does:

This program goes through each page and fetches all thumbnail's resolution to decide if the aspect ratio qualifies for a 4:3 at least.

For example 350x350 would mean a 1:1 aspect ratio and fail, but 350x233 qualifies as a wider than 4:3 aspect ratio. 

You can change the minimum aspect ratio from line 86:

    def aspect_ok(width, height):
        if not width or not height or height == 0:
            return False
        return (width / height) >= (4 / 3)

Whereas 4:3 is the default.

It will very likely go through all pages of your chosen tags due to Gelbooru's very lenient API calls limit. I've been able to fetch 3k-4k images going through hundreds of pages.

## Change to using an API key as of V3

So with V1 and V2 the scripts would use an HTML scraping based method so you don't have to input your own API key and keeps it simpler. Unfortunately in my testing as of lately this method, even with attempted changes, doesn't work anymore and I had to resort to the API key method. Which is one more step involved, but such is such.

## Other remarks

This script was done using Google Gemini as I'm a very novice programmer, but from my testing it definitely works and goes through all page results to not miss anything.

I've made this in tandem with a Danbooru version whereas if you're a collector I'd recommend utilizing both scripts since some posts can be exclusively on either Gelbooru or Danbooru and you can combine the resulting downloads of both pulls together, delete duplicates with a file organizer like Czkawka with an exact file size matcher and duplicate image detector especially useful for multi-variant artworks.
