# maskedhunter
A tool to scan sites while hiding behind proxies. Find the real IP addresses of the sites that sites which might be under proxy services like cloudflare.

## Installation 
`npm install anonlive/maskedhunter`

## Usage
`shotgun [options] url`

## Options
1. -s or --start: Specify IP range start address. Default: 0.0.0.0
2. -e or --end: Specify IP range end. Default: 255.255.255.255
3. -p or --port: Specify port to check. Default: 80/443 depending on the protocol

## Output
Write to stdout all the IPs that return status code 200s or 300s (most likely the right server).

## Configuration
Configure config.json in the format:
```JSON
[
  {
  host: "<socks5 proxy host ip>",
  port: <socks5 proxy host port>,
  username: "<socks5 proxy host username>",
  password: "<socks5 proxy host password>"
  },
  {
  host: "<socks5 proxy host ip>",
  port: <socks5 proxy host port>,
  username: "<socks5 proxy host username>",
  password: "<socks5 proxy host password>"
  },
  ...
]
```
All the scanning is done on the above configuration in a round-robin fashion.
