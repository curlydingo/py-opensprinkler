# py-opensprinkler

Python module for OpenSprinker API. Tested against OpenSprinkler version 2.1.9.

## Installation

```
pip install pyopensprinkler
```

## Usage

```python
from pyopensprinkler import Controller as OpenSprinklerController

controller = OpenSprinklerController("http[s]://hostname[:port]", "password")
controller.refresh()

version = controller.firmware_version
```

## Commands

### Controller

`controller.refresh()`
Refreshes state, programs and stations

`controller.enable()`
Enabled controller operation

`controller.disable()`
Disables controller operation

`controller.programs`

`controller.stations`


### Programs

```python
is_enabled = controller.programs[0].enabled

program = controller.programs[0]
program.run()
```

`program.enabled`

`program.enable()`

`program.disable()`

`program.run()`

### Stations

```python
is_enabled = controller.stations[0].enabled
status = controller.stations[0].status
station = controller.station[0]
station.run(120)
```

`station.is_running`

`station.running_program_id`

`station.status`

`station.run(seconds)`
 Acceptable range for seconds is 0 to 64800 (18 hours)

`station.stop()`

`station.toggle()`

# Development

- https://openthings.freshdesk.com/support/solutions/articles/5000716363-os-api-documents

```
virtualenv .
source bin/activate
pip install -r requirements.txt
deactivate
```
