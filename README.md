# hlsplayer
A single file you could drop into a S3 bucket to provide a player for the HLS video files there. I use this for hosting copies of live streams. It's dependent on the query string provided, this can be considered a key to the directory containing the HLS files. If bucket listing is turned off, this is probably secure enough.

## [Example instance](https://s3.aly.pet/stream/index.html?bbb)

Directory structure:

```
/index.html
/hls/<slug>/master.m3u8
/hls/<slug>/720p.m3u8
/hls/<slug>/1.ts
```

Given a query such as `?bbb`, it requests `./hls/<slug>/master.m3u8`, where slug is the query string without the leading ?. This [master.m3u8](https://github.com/alyssadev/hlsplayer/blob/main/example/master.m3u8) points to the various quality options. The player supports chapters and captions.
