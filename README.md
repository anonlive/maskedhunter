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

## Example
```
./shotgun -s 37.221.165.0 -e 37.221.165.255 http://anonfiles.com
37.221.165.204
37.221.165.209
37.221.165.76
37.221.165.205
37.221.165.207
37.221.165.201
37.221.165.78
37.221.165.210
37.221.165.212
37.221.165.202
37.221.165.208
37.221.165.149
37.221.165.222
37.221.165.136
37.221.165.138
37.221.165.151
37.221.165.145
37.221.165.141
37.221.165.140
37.221.165.19
37.221.165.9
37.221.165.5
37.221.165.17
37.221.165.7
37.221.165.16
37.221.165.77
37.221.165.75
37.221.165.22
37.221.165.74
37.221.165.170
37.221.165.150
37.221.165.137
37.221.165.144
37.221.165.135
37.221.165.148
37.221.165.143
37.221.165.4
37.221.165.155
37.221.165.147
37.221.165.154
37.221.165.139
37.221.165.130
37.221.165.132
37.221.165.131
37.221.165.134
37.221.165.133
37.221.165.162
37.221.165.157
37.221.165.156
37.221.165.153
37.221.165.146
37.221.165.142
37.221.165.158
37.221.165.152
```
