# Vita
![release](https://github.com/junnlikestea/vita/workflows/release/badge.svg)
[![Build status](https://github.com/junnlikestea/vita/workflows/Continuous%20integration/badge.svg)](https://github.com/junnlikestea/vita/actions)

### Installation
Precompiled binaries for vita are available in the [releases](https://github.com/junnlikestea/vita/releases) tab. Just pick your platform and extract the archive that contains the binary.

## Building it yourself 
If you want to build it yourself you will need to install Rust, you can get the [official installation](https://www.rust-lang.org/tools/install) from the Rust website.

To build Vita:
```
$ git clone https://github.com/junnlikestea/vita
$ cd vita
$ cargo build --release
$ ./target/release/vita --version
```

### Usage
With a single domain, and collect data from Apis' which don't require keys.:
```
vita -d hackerone.com
```

With a list of domains from a file:
```
vita -f path/to/domains.txt
```

With a list of domains from stdin:
```
vita < /path/to/domains.txt
```

if you want to include sources which require API keys, add the `-a` or `-all` flag, for example:
```
vita -d hackerone.com -a
``` 

### Sources
* AnubisDB
* Alienvault
* Binaryedge - be careful running this on a large host if you have a free license. Vita fetches every page of results.
* Certspotter
* Crt.sh
* Hackertarget
* Threatcrowd
* VirusTotal
* Sublis3r
* Security Trails
* Spyse
* Urlscan.io
* Facebook
* Threatminer
* wayback machine
* dns.bufferover.run

### How to set your Api Keys
Add a `.env` file to the directory, and set the following variables:
* Binaryedge:
	* Needs `BINARYEDGE_TOKEN` set
* Facebook:
	* Needs `FB_APP_ID` and `FB_APP_SECRET` set.
* Spyse:
	* Needs `SPYSE_TOKEN` set.
* Security Trails:
	* Needs `SECURITY_TRAILS_KEY` set.

If you hit rate limits or authentication fails, you will get a message in `stderror`, this will not
be printed in the final output.
### To-do
* Add more paid sources.
* Clean up some data stuctures and methods.
* Optimise performance further.
### Disclaimer
Developers have/has no responsibility or authority over any kind of:
* Legal or Law infringement by third parties and users.
* Malicious use capable of causing damage to third parties.
* Illegal or unlawful use of vita.

Thanks to [0xatul](https://twitter.com/atul_hax) for the feedback!
