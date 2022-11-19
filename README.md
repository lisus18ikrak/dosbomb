

## What is dosbomb?
dosbomb is basically an HTTP Denial of Service attack that affects threaded servers. It works like this:

1. it start making lots of HTTP requests.
2. it send headers periodically (every ~15 seconds) to keep the connections open.
3. it never close the connection unless the server does so. If the server closes a connection, it create a new one keep doing the same thing.

This exhausts the servers thread pool and the server can't reply to other people.


## How to install and run?


If you want to clone using git, here's how you do it.

* `git clone https://github.com/lisus18ikrak/dosbomb.git`
* `cd dosbomb`
* `python3 dosbomb.py example.com` or
* `python3 dosbomb.py -p -v  example.com`

### SOCKS5 proxy support

However, if you plan on using the `-x` option in order to use a SOCKS5 proxy for connecting instead of a direct connection over your IP address, you will need to install the `PySocks` library (or any other implementation of the `socks` library) as well. [`PySocks`](https://github.com/Anorov/PySocks) is a fork from [`SocksiPy`](http://socksipy.sourceforge.net/) by GitHub user @Anorov and can easily be installed by adding `PySocks` to the `pip` command above or running it again like so:

* `sudo pip3 install PySocks`

You can then use the `-x` option to activate SOCKS5 support and the `--proxy-host` and `--proxy-port` option to specify the SOCKS5 proxy host and its port, if they are different from the standard `127.0.0.1:8080`.

## Configuration options
It is possible to modify the behaviour of dosbomb with command-line
arguments. In order to get an up-to-date help document, just run
`python3 dosbomb.py -h`.
* -p, --port
* * Port of webserver, usually 80
* -s, --sockets
* * Number of sockets to use in the test
* -v, --verbose
* * Increases logging (output on terminal)
* -ua, --randuseragents
* * Randomizes user-agents with each request
* -x, --useproxy
* * Use a SOCKS5 proxy for connecting
* --https
* * Use HTTPS for the requests
* --sleeptime
* * Time to sleep between each header sent






<h5>Note:</h6>
If you find any problems than please write on issue github and to our Telegram Group. Don't use for revenge! Make sure your anonymity! It's made for just testing purpose. We are not responsible for any abuse or damage caused by this program. Only for Educational Purpose. Thanks.
