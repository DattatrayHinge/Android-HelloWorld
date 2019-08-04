# MyAndroidHelloWorld
Dattatray First Hello World Repository
```nodjes
    // Client is connected now set clyclic trigger to send time update 
    // service on every 1 sec. 
    setInterval(function timeout() {
        // Check client is alive or not 
        if(ws.readyState===WebSocket.OPEN){
            // Send time update service
            ws.send(JSON.stringify({service:'TIME_UPDATE', 
            timestamp: Date.now()}));
        }
    }, 1000);
```
```nodejs
         // Data received handler 
        ws.on('message', function incoming(data) {
            var obj = JSON.parse(data);
            if(obj.service ==="TIME_UPDATE"){
                console.log(`Received Timestamp Update: Roundtrip Time: ${Date.now() - obj.timestamp} ms`);
            }else {
                console.log(`Unknown Service: ${obj.service}`);
            }
        });
```
