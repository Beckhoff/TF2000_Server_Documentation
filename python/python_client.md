# Client API for the TwinCAT HMI Server

This module provides an asynchronous client for interacting with Beckhoff PLCs via the TwinCAT HMI Server.
It supports reading, writing, and subscribing to PLC variables and any other HMI Server symbols.

Usage:

```python
from beckhoff.tchmi.client import Command, Session

async with Session('wss://localhost:2020',
                   user='__SystemAdministrator',
                   password='1') as session:
    # Read a PLC variable.
    counter: int = await session.request(Command('ADS.PLC1.MAIN.nCounter'))

    # Write a PLC array.
    await session.request(Command('ADS.PLC1.MAIN.aNames', ['foo', 'bar']))

    # Subscribe to get notified about value changes. Subscriptions and requests can also
    # use multiple symbols.
    async for command, _ in session.subscribe([Command('Diagnostics::SERVERTIME'), Command('Diagnostics::UPTIME')],
                                              interval_time=50, extract_read_value=False):
        print(f'Received a subscription tick. {command.symbol}: {command.readValue}')
```

## Error

```python
@dataclass
class Error(JsonSerializable)
```

#### code: `int`

Integer representing the HMI error code.

#### domain: `Optional[str]`

The domain of the error.

#### message: `Optional[str]`

String representation of the error code, e.g. 'HMI_E_UNEXPECTED'.

#### reason: `Optional[str]`

Additional information regarding the error.

## Command

```python
@dataclass
class Command(JsonSerializable)
```

Represents a command sent to the TwinCAT HMI Server.

#### symbol: `str`

#### writeValue: `Any`

#### readValue: `Any`

#### version: `Optional[float]`

#### commandOptions: `Optional[List[str]]`

#### error: `Optional[Error]`

#### symbolOptions: `Any`

#### customerData: `Optional[str]`

#### disabledCommandOptions: `Optional[List[str]]`

#### commandIndex: `Optional[int]`

#### filter: `Optional[Any]`

#### filterMap: `Optional[List[int]]`

#### limit: `Optional[int]`

#### offset: `Optional[int]`

#### orderBy: `Optional[str]`

#### maxSubSymbolDepth: `Optional[float]`

#### maxEntries: `Optional[int]`

#### extensionData: `Optional[Any]`

#### from\_dict

```python
@classmethod
def from_dict(cls: Type[T], data: dict) -> T
```

## Request

```python
@dataclass
class Request(JsonSerializable)
```

#### requestType: `str`

Type of the request, either `ReadWrite` or `Subscription`.

#### commands: `List[Command]`

#### customerData: `Optional[str]`

#### apiVersion: `Optional[float]`

#### serverTiming: `Optional[Any]`

#### id: `float`

#### sessionId: `Optional[str]`

#### intervalTime: `Optional[int]`

#### error: `Optional[Error]`

#### has\_error

```python
def has_error() -> bool
```

Returns True if the request has or any command has an error.

## Session

```python
class Session()
```

Represents an asynchronous session with the TwinCAT HMI Server.

#### request

```python
@overload
async def request(commands: Command,
                  extract_read_value: Literal[True] = True) -> Any
```

#### request

```python
@overload
async def request(commands: Command,
                  extract_read_value: Literal[False] = ...) -> Command
```

#### request

```python
@overload
async def request(commands: List[Command],
                  extract_read_value: Literal[True] = True) -> List[Any]
```

#### request

```python
@overload
async def request(commands: List[Command],
                  extract_read_value: Literal[False] = ...) -> List[Command]
```

#### request

```python
async def request(
    commands: List[Command] | Command,
    extract_read_value: bool = True
) -> List[Command] | List[Any] | Command | Any
```

Read, write, or invoke multiple HMI server symbols and return the Command objects.

**Arguments**:

- `session` - The session object.
- `commands` - List of command objects or a single command object.

**Returns**:

  The command objects or the read values, if extract_read_value is true.
  
```python
# Write a PLC array.
await session.request(Command('ADS.PLC1.MAIN.aNames', ['foo', 'bar']))

# Read a PLC variable.
counter: int = await session.request(Command('ADS.PLC1.MAIN.nCounter'))
```

#### subscribe

```python
@overload
def subscribe(
    commands: List[Command],
    interval_time: int = 200,
    extract_read_value: Literal[True] = True
) -> AsyncIterator[Tuple[Any, float]]
```

#### subscribe

```python
@overload
def subscribe(
    commands: List[Command],
    interval_time: int = 200,
    extract_read_value: Literal[False] = ...
) -> AsyncIterator[Tuple[Command, float]]
```

#### subscribe

```python
@overload
def subscribe(
    commands: Command,
    interval_time: int = 200,
    extract_read_value: Literal[True] = True
) -> AsyncIterator[Tuple[Any, float]]
```

#### subscribe

```python
@overload
def subscribe(
    commands: Command,
    interval_time: int = 200,
    extract_read_value: Literal[False] = ...
) -> AsyncIterator[Tuple[Command, float]]
```

#### subscribe

```python
async def subscribe(
    commands: List[Command] | Command,
    interval_time: int = 200,
    extract_read_value: bool = True
) -> AsyncIterator[Tuple[Any | Command, float]]
```

Subscribe to a HMI server symbol and yield its values.

**Arguments**:

- `session` - The session object.
- `commands` - List of command objects or a single command object.
- `interval_time` - The interval time in milliseconds.
  

**Yields**:

  The subscription id and the command object or the read value if extract_read_value is true.
  
```python
# subscribe to Diagnostics::SERVERTIME
async for value, _ in session.subscribe(Command('Diagnostics::SERVERTIME'),
                                          interval_time=50):
    print(f'Received a subscription tick. The current server time is {value}')
```

#### open

```python
async def open() -> None
```

#### close

```python
async def close() -> None
```

