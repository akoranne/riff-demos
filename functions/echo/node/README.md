echo-node
===

The "Hello World" of Riff, the echo-node function takes in a string and echos it back at the user

Build the Function
---
```
riff build -n echo-node -v 0.0.1 -f .
```

Apply the Function
---
```
riff apply -f .
```

Call the Function
---
If you havn't already, ensure your shell environment is setup with the Riff HTTP Gateway
```
export GATEWAY=`minikube service --url demo-riff-http-gateway`
export HEADER="Content-Type: text/plain"
```

And then call the function
```
curl $GATEWAY/requests/echo-node -H "$HEADER" -d "Hello World"
```

Which will return:
```
Echoing: Hello World
```