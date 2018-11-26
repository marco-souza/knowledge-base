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


class CustomJsonEncoder(json.JSONEncoder):

    def default(self, obj):
        if isinstance(obj, datetime.datetime):
            return obj.strftime("%d/%m/%Y")

        return json.JSONEncoder.default(self, obj)


def get_logger():
    logger = logging.getLogger('pysmartt')
    return logger


def setup_logger(logger):
    formatter = jsonlogger.JsonFormatter(
        "(asctime) (levelname) (module) (funcName) (lineno) (message)",
        json_encoder=CustomJsonEncoder
    )
    logHandler = logging.StreamHandler()
    logHandler.setFormatter(formatter)
    logger.addHandler(logHandler)
    logger.propagate = False

```