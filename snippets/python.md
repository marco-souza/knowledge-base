# Python Snippets and notes


## Set system timezone in python

```python
def set_timezone():
    """Set global timezone."""
    timezone = "America/Sao_Paulo"
    os.environ['TZ'] = timezone
    time.tzset()
```