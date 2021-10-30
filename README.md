# Movie Quote Twitter Bot Ansible role

## This is a WIP

The project depends on the collection `community.docker` but apparently this [cannot be listed as a dependency](https://github.com/ansible/ansible/issues/62847) so make sure you add it to your `requirements.yml` file like:

```yml
---

collections:
  - community.docker

roles:
  - src: https://github.com/namelivia/namelivia.moviequotetwitterbot
```

## Required variables

 - `cloudwatch_region` Cloudwatch region to send the logs to.
 - `cloudwatch_log_group` Cloudwatch log group to send the logs to.
 - `consumer_key`: Your Twitter account consumer key.
 - `consumer_secret`: Your Twitter account consumer secret.
 - `access_token_key`: Your Twitter account access token key.
 - `access_token_secret`: Your Twitter account access token secret.
 - `subs_uri`: Path of the .srt subs file. e.g. `/home/user/movies/movie.srt`
 - `subs_encoding`: Encoding of the subs file. e.g. `utf-8-sig`, `latin-1`, etc... 
 - `video_uri`: Path of the actual movie file. e.g. `/home/users/movies/movie.mkv`
 - `output_uri`: Path where the GIF file that will be posted is stored. e.g. `/tmp/movie.gif`
 - `text_color`: Color for the text that will be displayed e.g. `yellow`, `white`, etc...
 - `text_size`: Font size for the text that will be displayed e.g. `18`
 - `text_font`: Font for the text that will be displayed e.g. `FreeSans-Negrita`
 - `idle_period`: The number of seconds the script will wait before executing. e.g. `900`

 ## Uploading a movie and subtitles file
 
 Once the application deploys it creates a folder called `movies` on the user directory, you should upload there the movie and subtitles files.
