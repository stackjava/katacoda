##### Connect to SocketCluster Server (Tradex-WS)

To connect to SocketCluster Server, we use method <pre>create</pre> (or <pre>connect</pre> for socket-client version < v10.0.0)

<pre class="file" data-filename="client.js" data-target="replace">
var socketCluster = require('socketcluster-client');

var options = {
  port: 8000
};

// Initiate the connection to the server
var socket = socketCluster.create(options);

socket.on('connect', function () {
  console.log('CONNECTED');
});
</pre>

##### Connection Options
Options is optional,it's infomation contains port, host, security...
See all available options : https://socketcluster.io/#!/docs/api-socketcluster-client

<pre>
var options = {
  path: '/socketcluster/',
  port: 8000,
  hostname: '127.0.0.1',
  autoConnect: true,
  secure: false,
  rejectUnauthorized: false,
  connectTimeout: 10000, //milliseconds
  ackTimeout: 10000, //milliseconds
  channelPrefix: null,
  disconnectOnUnload: true,
  multiplex: true,
  autoReconnectOptions: {
    initialDelay: 10000, //milliseconds
    randomness: 10000, //milliseconds
    multiplier: 1.5, //decimal
    maxDelay: 60000 //milliseconds
  },
  authEngine: null,
  codecEngine: null,
  subscriptionRetryOptions: {},
  query: {
    yourparam: 'hello'
  }
};
</pre>

To connect to Tradex-WS, we use below options:
<pre>
var options = {
  port: 8000,
  hostname:'52.77.225.82'
  };
</pre>
