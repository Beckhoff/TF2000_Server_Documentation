# TwinCAT HMI Server Extension API Reference

The `beckhoff.tchmi.extensionapi` module provides an API for easier handling of websocket communication and event callbacks.

## Context

```python
@dataclass
class Context(JsonSerializable)
```

#### socketID: `Optional[int]`

Unique websocket ID of the request. Only set when the subscription has not been merged.

#### subscriptionID: `Optional[int]`

Unique subscription ID of the request. Only set when the request is a subscription.

#### locale: `str`

The locale of the client.

#### requestType: `str`

Type of the request, either `ReadWrite` or `Subscription`.

## ExtensionHost

```python
class ExtensionHost()
```

Base class for creating extensions.

#### on\_close\_websocket

```python
async def on_close_websocket(context: Context) -> None
```

Callback invoked when the websocket connection is closed.

#### on\_create\_websocket

```python
async def on_create_websocket(context: Context) -> None
```

Callback invoked when the websocket connection is first utilized for an extension request.

#### on\_subscribe

```python
async def on_subscribe(context: Context) -> None
```

Callback invoked when a new subscription is created.

#### on\_unsubscribe

```python
async def on_unsubscribe(context: Context) -> None
```

Callback invoked when the final subscriber has unsubscribed from the subscription.

#### on\_request

```python
async def on_request(context: Context, commands: List[Command]) -> None
```

Called when the server requests a symbol from the extension.

#### on\_config\_change

```python
async def on_config_change(context: Context, config: Dict[str, Any]) -> None
```

Callback triggered when the extension configuration is updated.

**Arguments**:

- `config` - The complete configuration settings for the extension.

#### init

```python
async def init(domain: str, settings: Dict[str, Any]) -> None
```

Initialize the extension with the provided domain and settings.

#### shutdown

```python
async def shutdown() -> None
```

Shutdown the extension and perform any necessary cleanup.

#### execute

```python
async def execute(commands: List[Command],
                  timeout: float = 5.0) -> List[Command]
```

Execute the provided commands and return the results.

This method sends a request and waits for the corresponding response within the specified timeout.

**Arguments**:

- `commands` - Commands to be executed.
- `timeout` - Timeout in seconds for the execution.

#### send

```python
async def send(name: str, payload: Any) -> None
```

Send an event with the specified name and payload to the HMI server.

#### run

```python
async def run() -> None
```

Start the extension.

