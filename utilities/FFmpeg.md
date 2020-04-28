
## Using ffmpeg to download m3u8 file into mp4

`ffmpeg -protocol_whitelist file,http,https,tcp,tls,crypto -i "${url}" -c copy "output.mp4"`