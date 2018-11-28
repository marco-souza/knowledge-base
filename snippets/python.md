# Python Snippets and notes


## Set system timezone in python

```python
def set_timezone():
    """Set global timezone."""
    timezone = "America/Sao_Paulo"
    os.environ['TZ'] = timezone
    time.tzset()
```

## Setup python json logger

```python
# which python
# -*- coding: utf-8 -*-
"""pysmartt utils"""
import json
import logging
import datetime
from pythonjsonlogger import jsonlogger


def get_logger(ns='cvm_crawler_api'):
    """Generate a json logger."""
    logger = logging.getLogger(ns)
    _setup_logger(logger)
    return logger


def _setup_logger(logger):
    formatter = jsonlogger.JsonFormatter(
        "(asctime) (levelname) (module) (funcName) (lineno) (message)"
    )
    logHandler = logging.StreamHandler()
    logHandler.setFormatter(formatter)
    logger.handlers = []
    logger.addHandler(logHandler)
    logger.propagate = False

```