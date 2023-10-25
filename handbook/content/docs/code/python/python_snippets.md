---
title: "Python Snippets"
weight: 1
desc: "Useful, copy-pastable python snippets and how to use them."
draft: false
---

# Python Snippets
*Useful, copy-pastable python snippets and how to use them.*

![Complete](https://img.shields.io/badge/status-draft-red?style=flat-square)

## Aim
This page lists some useful and copy-pastable snippets to keep handy when working with python.

## Setting up colored logging

This is a simple, colorful logging example that uses `colorama` to color the output in the console, and save the logs both in a rotating log file and the console. This usually lives in your module's `__init__.py`. Simply change the `root_logger` name, and the `LOG_FILE_PATH` (if you need file logging). The rest is handled for you.

```python
import os
from typing import Optional
import logging
from logging import StreamHandler
from logging.handlers import RotatingFileHandler
from colorama import Fore, Style, Back, init
from pathlib import Path

init(autoreset = True) # This sets up colorama.

# Setup (colored) logging
FORMAT: str = '%(asctime)s [%(levelname)s] %(name)s: %(message)s'
"""The format of the logging module messages"""
LOG_FILE_PATH: Optional[Path] = None
"""Path where to save the file log. Set to `None` to suppress file logging."""

# TODO: Change this to the name of the module. This is the root logger.
root_logger = logging.getLogger("MyModule")
root_logger.setLevel(logging.DEBUG) # Do not change this! The actual levels are sat later on.
root_logger.propagate = False

class ColorFormatter(logging.Formatter):
    # Change this dictionary to suit your coloring needs!
    COLORS = {
        "WARNING": Fore.YELLOW,
        "ERROR": Fore.RED,
        "DEBUG": Style.BRIGHT + Fore.MAGENTA,
        "INFO": Fore.GREEN,
        "CRITICAL": Style.BRIGHT + Fore.RED,
    }

    def format(self, record):
        reset = Fore.RESET + Back.RESET + Style.NORMAL
        color = self.COLORS.get(record.levelname, "")
        if color:
            record.name = Style.BRIGHT + Fore.BLUE + record.name + reset
            if record.levelname != "INFO":
                record.msg = color + record.msg + reset
            record.levelname = color + record.levelname + reset
        return logging.Formatter.format(self, record)

console_formatter = ColorFormatter(FORMAT)

# If you don't need file logging, this can be deleted
if LOG_FILE_PATH:
    os.makedirs(_LOG_PATH.parent, exist_ok = True)
    file_formatter = logging.Formatter(format)
    file_h = RotatingFileHandler(
        filename=Path(_LOG_PATH),
        encoding="utf-8",
        mode="a+",
        maxBytes=1e5,
        backupCount=5,
    )
    file_h.setFormatter(file_formatter)
    file_h.setLevel(logging.DEBUG) # The level of the file log is set here.
    root_logger.addHandler(file_h)

stream_h = StreamHandler()
stream_h.setFormatter(console_formatter)
stream_h.setLevel(logging.DEBUG) # The level of the stream log is set here.
root_logger.addHandler(stream_h)
```

Note: In a small script, or in other places where you do not need pretty logging, you can just run [`logging.basicConfig()`](https://docs.python.org/3/library/logging.html#logging.basicConfig) to start logging faster.

