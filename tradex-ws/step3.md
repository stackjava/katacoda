Subscribe channel from Tradex-WS
In this tutorial, I will create node.js client:

create file _client.js_ with following content:

<pre class="file" data-filename="client.js" data-target="replace">
var socketCluster = require('socketcluster-client');

var options = {
  port: 8000,
  hostname:'52.77.225.82'
  };

// Initiate the connection to the server
var socket = socketCluster.create(options);

socket.on('connect', function () {
  console.log('CONNECTED');
});

//-------------------------------------------
var bidOfferChannel = socket.subscribe('market.stock.bidoffer');
bidOfferChannel.on('subscribeFail', function (err) {
console.error('Failed to subscribe to the bidOfferChannel channel due to error: ' + err);
});

bidOfferChannel.watch(function (data) {
console.log('bidOfferChannel: ', data);
});
</pre>


*options*: options when connect to server (port, host, security...)
(See more in: https://socketcluster.io/#!/docs/api-socketcluster-client)

###### Run client.js with node.js
`node client.js`{{execute}}
