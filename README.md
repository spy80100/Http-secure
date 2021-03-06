# Http-secure

Python script to check HTTP security headers

 Python script. checks some server/version headers. Written and tested using Python 3.4.

With minor modifications could be used as a library for other projects.

Usage
$ python sh.py --help
usage: sh.py [-h] [--max-redirects N] URL

Check HTTP security headers

positional arguments:
  URL                Target URL

optional arguments:
  -h, --help         show this help message and exit
  --max-redirects N  Max redirects, set 0 to disable (default: 2)
$
Output
$ python sh.py --max-redirects 5 https://xxxxx.com
Header 'x-xss-protection' is missing ... [ WARN ]
Header 'x-content-type-options' is missing ... [ WARN ]
Header 'content-security-policy' is missing ... [ WARN ]
Header 'x-powered-by' is missing ... [ OK ]
Header 'x-frame-options' contains value 'DENY' ... [ OK ]
Header 'strict-transport-security' contains value 'max-age=63072000' ... [ OK ]
Header 'access-control-allow-origin' is missing ... [ OK ]
Header 'server' contains value 'nginx/1.10.1' ... [ WARN ]
HTTPS supported ... [ OK ]
HTTPS valid certificate ... [ OK ]
HTTP -> HTTPS redirect ... [ OK ]
$
