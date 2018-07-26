Subscribe channel from Tradex-WS

Create object to subscribe channel and watch for incoming data which is published on that channel by other clients or the server

To create object subscribe channel, you can use method <pre>subscribe</pre> with channel name:

**Example:**
<pre>
var bidOfferChannel = socket.subscribe('market.stock.bidoffer');
  bidOfferChannel.on('subscribeFail', function (err) {
  console.error('Failed to subscribe to the bidOfferChannel channel due to error: ' + err);
  });

bidOfferChannel.watch(function (data) {
  console.log('bidOfferChannel: ', data);
  });
</pre>

- Method <pre>on</pre>: Capture event (subscribe, unsubscribe, subscribeFail... )
- Method <pre>watch</pre>: Capture any data which is published to this channel

See all properties, events, method here: https://socketcluster.io/#!/docs/api-scchannel-client
