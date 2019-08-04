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
