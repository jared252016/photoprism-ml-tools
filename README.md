# pp-cli - v0.0.1
## Simple auth tool in python for PhotoPrism. Returns the token. 
Usage:
- pp-cli help


## Goals

Usage: 
- pp-cli [search|config|help|image|video|album|label] [add|ls|rm|inspect|append|set|get|help]

Setup:
- pp-cli config set host=localhost protocol=https port=4444 base=/v1/api

Examples:
- pp-cli search apple --type video

- pp-cli image add [path_to_image] --name "Test Image" --labels apple,red,sfw

- pp-cli image set label=apple,red,sfw

- pp-cli album add [album-name]

- pp-cli album add [album-name] [image|video-name]

- pp-cli label add [label-name] [image|video]

- pp-cli album rm [album-name]

- pp-cli album ls [partial-name]
