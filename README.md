# pp-cli - v0.0.1
## Description
Simple auth tool in python for PhotoPrism. Returns the token. 
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

# pp-proxy - v0.0.1
## Description
pp-proxy is a simple websocket client for PhotoPrism's API that forwards requests to webhook urls. Supports queueing (sync) or async with rate limiting (eventually). Intended to work with something like n8n to automate machine learning proceses and ultimately run additional labelers.

### Usage: 
- pp-proxy start [host] [password]

### Example Config
###
webhook:
  name: file-add-hook
  filter: event # Other option is foward-all
  queue: False # Do not bother with queueing them, just send them in random order.
  rate-limit: False # Max of % requests / minute. False if using queue.
  event:
    - index.indexing
  url: https://localhost/webhook/50a3e896-c180-43a3-8e87-00d4987cde97
  method: POST
###

# pp-labeler
## Description
[Not started] pp-labeler is a tool that adds labels based on pre-trained models that are trained seperately on a remote host via WebDAV and the PhotoPrism API. The idea is to have a folder of "labeler" yml files that are essentially exports of the pre-trained models and any necessary config. You should be able to add a model using purely yml. With this, in theory you would not be bogged down to tensorflow either, so will keep in mind making it modular. 

# pp-train
## Description
[Not Started] pp-train ingests all the data from a photoprism instance by label and trains a model based on this data. Supports Websocket API and WebDAV.
