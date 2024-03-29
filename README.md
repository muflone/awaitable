# Awaitable

[![Travis CI Build Status](https://img.shields.io/travis/com/muflone/awaitable/master.svg)](https://www.travis-ci.com/github/muflone/awaitable)
[![CircleCI Build Status](https://img.shields.io/circleci/project/github/muflone/awaitable/master.svg)](https://circleci.com/gh/muflone/awaitable)
[![PyPI - Version](https://img.shields.io/pypi/v/Awaitable.svg)](https://pypi.org/project/Awaitable/)
[![PyPI - Python Version](https://img.shields.io/pypi/pyversions/Awaitable.svg)](https://pypi.org/project/Awaitable/)

**Description:** A decorator to asynchronously execute synchronous functions

**Copyright:** 2022 Fabio Castelli (Muflone) <muflone@muflone.com>

**License:** GPL-3+

**Source code:** https://github.com/muflone/awaitable

**Documentation:** http://www.muflone.com/awaitable/

# Description

Awaitable is a small decorator to asynchronously execute synchronous functions.

# System Requirements

* Python 3.x

# Usage

You can decorate a synchronous routine using `@awaitable.awaitable` to make it
awaitable and `awaitable.AsyncioGather` to process some tasks using asyncio:

```python
import awaitable

@awaitable.awaitable
def do_something():
    # process a single task
    return

async def process(count):
    # execute some workers
    tasks = awaitable.AsyncioGather()
    for i in range(count):
        tasks.add(do_something())
    await tasks.run()

awaitable.run_awaitable(func=process, count=10)
```

Please see the **samples** folders for some others usage examples.
