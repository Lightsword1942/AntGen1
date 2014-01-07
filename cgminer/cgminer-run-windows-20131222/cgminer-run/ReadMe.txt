This is a multi-threaded multi-pool AntMiner U1 for bitcoin.

EXECUTIVE SUMMARY ON USAGE:

Single pool:

cgminer -o http://pool:port -u username -p password

Multiple pools:

cgminer -o http://pool1:port -u pool1username -p pool1password -o http://pool2:port -u pool2usernmae -p pool2password

Single pool with a standard http proxy:

cgminer -o "http:proxy:port|http://pool:port" -u username -p password

Single pool with a socks5 proxy:

cgminer -o "socks5:proxy:port|http://pool:port" -u username -p password

Single pool with stratum protocol support:

cgminer -o stratum+tcp://pool:port -u username -p password

The list of proxy types are:
 http:    standard http 1.1 proxy
 http0:   http 1.0 proxy
 socks4:  socks4 proxy
 socks5:  socks5 proxy
 socks4a: socks4a proxy
 socks5h: socks5 proxy using a hostname

---

Usage instructions:  Run "cgminer --help" to see options:

Usage: cgminer [-DdElmpPQqUsTouOchnV]

Options for both config file and command line:
--api-allow         Allow API access (if enabled) only to the given list of [W:]IP[/Prefix] address[/subnets]
                    This overrides --api-network and you must specify 127.0.0.1 if it is required
                    W: in front of the IP address gives that address privileged access to all api commands
--api-description   Description placed in the API status header (default: cgminer version)
--api-groups        API one letter groups G:cmd:cmd[,P:cmd:*...]
                    See API-README for usage
--api-listen        Listen for API requests (default: disabled)
                    By default any command that does not just display data returns access denied
                    See --api-allow to overcome this
--api-network       Allow API (if enabled) to listen on/for any address (default: only 127.0.0.1)
--api-mcast         Enable API Multicast listener, (default: disabled)
                    The listener will only run if the API is also enabled
--api-mcast-addr <arg> API Multicast listen address, (default: 224.0.0.75)
--api-mcast-code <arg> Code expected in the API Multicast message, don't use '-' (default: "FTW")
--api-mcast-port <arg> API Multicast listen port, (default: 4028)
--api-port          Port number of miner API (default: 4028)
--balance           Change multipool strategy from failover to even share balance
--benchmark         Run cgminer in benchmark mode - produces no shares
--compact           Use compact display without per device statistics
--debug|-D          Enable debug output
--device|-d <arg>   Select device to use, one value, range and/or comma separated (e.g. 0-2,4) default: all
--disable-rejecting Automatically disable pools that continually reject shares
--expiry|-E <arg>   Upper bound on how many seconds after getting work we consider a share from it stale (default: 120)
--failover-only     Don't leak work to backup pools when primary pool is lagging
--fix-protocol      Do not redirect to a different getwork protocol (eg. stratum)
--hotplug <arg>     Set hotplug check time to <arg> seconds (0=never default: 5) - only with libusb
--kernel-path|-K <arg> Specify a path to where bitstream files are (default: "/usr/local/bin")
--load-balance      Change multipool strategy from failover to quota based balance
--log|-l <arg>      Interval in seconds between log output (default: 5)
--lowmem            Minimise caching of shares for low memory applications
--monitor|-m <arg>  Use custom pipe cmd for output messages
--net-delay         Impose small delays in networking to not overload slow routers
--no-submit-stale   Don't submit shares if they are detected as stale
--pass|-p <arg>     Password for bitcoin JSON-RPC server
--per-device-stats  Force verbose mode and output per-device statistics
--protocol-dump|-P  Verbose dump of protocol-level activities
--queue|-Q <arg>    Minimum number of work items to have queued (0 - 10) (default: 1)
--quiet|-q          Disable logging output, display status and errors
--real-quiet        Disable all output
--remove-disabled   Remove disabled devices entirely, as if they didn't exist
--rotate <arg>      Change multipool strategy from failover to regularly rotate at N minutes (default: 0)
--round-robin       Change multipool strategy from failover to round robin on failure
--scan-time|-s <arg> Upper bound on time spent scanning current work, in seconds (default: 60)
--sched-start <arg> Set a time of day in HH:MM to start mining (a once off without a stop time)
--sched-stop <arg>  Set a time of day in HH:MM to stop mining (will quit without a start time)
--sharelog <arg>    Append share log to file
--shares <arg>      Quit after mining N shares (default: unlimited)
--socks-proxy <arg> Set socks4 proxy (host:port) for all pools without a proxy specified
--syslog            Use system log for output messages (default: standard error)
--temp-cutoff <arg> Temperature where a device will be automatically disabled, one value or comma separated list (default: 95)
--text-only|-T      Disable ncurses formatted screen output
--url|-o <arg>      URL for bitcoin JSON-RPC server
--user|-u <arg>     Username for bitcoin JSON-RPC server
--verbose           Log verbose output to stderr as well as status output
--userpass|-O <arg> Username:Password pair for bitcoin JSON-RPC server
Options for command line only:
--config|-c <arg>   Load a JSON-format configuration file
See example.conf for an example configuration.
--help|-h           Print this message
--version|-V        Display version and exit

AntMiner U1 device options:
--bmsc-options <arg> Set specific device board configurations - one set of values for all or comma separated
--bmsc-freq <arg> Set work frequency
--bmsc-rdreg <arg> Get reg value

eg:
--bmsc-options 115200:20
The values are baud : timeout, and timeout is 20 * 100ms

--bmsc-freq 4F02
The value following:
0581 : 150M
0681 : 175M
4F02 : 193M
0781 : 200M
0881 : 225M
0981 : 250M
0A81 : 275M
0B81 : 300M
0C81 : 325M
0D81 : 350M
0E81 : 375M
0F81 : 400M
5081 : 425M
5181 : 450M
5281 : 475M
5381 : 500M

