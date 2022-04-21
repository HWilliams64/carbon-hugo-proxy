# Carbon Hugo Proxy

This is a simple single file reverse proxy that serves static files generated by [Hugo](https://gohugo.io/). This proxy is meant to be run with in a [Grader Than Carbon Workspace](https://www.graderthan.com/service/). 

## Getting Started

To run the proxy:

```shell
./hugo_proxy path/to/your/hugo/project
```

By default the server will listen on port 8000. You can edit this with the agrument `-p`. Example:

```shell
./hugo_proxy path/to/your/hugo/project -p 12345
```

## Motivation

My students want to develop static websites with Hugo on their Carbon Workspaces so they can easily share their content with the world. Many Hugo themes don't handle running from a subdomain well. When hosting the site from the Carbon Workspace, their content is in the Workspace's subdomain. This project was created to resolve this issue. 

## How It Works

1) Starts the Hugo Server and renders the files to disk.
2) Starts a python HTTPServer
3) The users connect to the HTTPServer instead of the Hugo server. Each request loads the rendered Hugo files.
4) If the user makes an edit to their Hugo content, the Hugo server re-renders the files.


## Limitations 

**THIS IS MEANT FOR EDUCATIONAL PURPOSES ONLY!!!** If you need something more substantial, please use [Nginx](https://www.nginx.com/) or [Appache](https://httpd.apache.org/)
