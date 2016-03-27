<img src="https://i.imgur.com/scqdu3p.png" width="400">

# statstrmr
#### _JSON-HEP_ Statistics Streamer for HOMER 5.x

<img src="http://i.imgur.com/74Gswvq.gif" />

### Description

statstrmr is a simple PoC tool to stream HEP-JSON formatted statistics to a HOMER 5 [HTTP API](https://github.com/sipcapture/homer/wiki/Example%3A-CustomStats) Instance

### Status

* Status: Experimental

### Install
<pre>
npm install
</pre>

### Config
Copy and edit ```config.js``` with your HOMER ```API_SERVER``` and ```API_PATH``` details and logfile path/tags<br>
<pre>
cp config.js myconfig.js
</pre>

Each LOGS entry requires/defines a log path and a _(regex)_ **pattern** to match the "type" field from each JSON object
<pre>
var config = {
        API_SERVER: 'http://127.0.0.1',
        API_PATH: '/api/v1/stats/push',
        LOGS: [
                {
                  tag : 'custom_tag',
                  host : 'your_hostname',
                  <b>pattern: 'report_id',</b> // matching JSON: "type":"report_id" 
                  path : '/path/to/your.log'
                }
              ]
};
</pre>

### Test
<pre>
nodejs statsstrmr.js -c ./myconfig.js
</pre>

### Configure
Copy your final application parameters for API and LOGS monitoring in ```config.js``` and run ```forever```
```
npm forever
```

### Example Output in HOMER 5
![](http://i.imgur.com/ztmTUFr.png)

Learn how to use this extension with real data on the [HOMER Wiki](https://github.com/sipcapture/homer/wiki/Example%3A-CustomStats)


---------

### Developers
Contributions to our projects are always welcome! If you intend to participate and help us improve our software, we kindly ask you to sign a [CLA (Contributor License Agreement)](http://cla.qxip.net) and coordinate at best with the existing team via the [homer-dev](http://groups.google.com/group/homer-dev) mailing list.


----------


##### If you use our projects in production, please consider supporting us with a [donation](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=donation%40sipcapture%2eorg&lc=US&item_name=SIPCAPTURE&no_note=0&currency_code=EUR&bn=PP%2dDonationsBF%3abtn_donateCC_LG%2egif%3aNonHostedGuest)

[![Donate](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=donation%40sipcapture%2eorg&lc=US&item_name=SIPCAPTURE&no_note=0&currency_code=EUR&bn=PP%2dDonationsBF%3abtn_donateCC_LG%2egif%3aNonHostedGuest)



