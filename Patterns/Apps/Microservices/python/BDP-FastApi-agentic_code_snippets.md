# Code snippets — core package

Tiny example stubs for the `core/` package (compact starting points).

## core/config.py
```python
from pydantic import BaseSettings

class Settings(BaseSettings):
    app_name: str = "my-service"
    debug: bool = False

    class Config:
        env_file = ".env"

def get_settings() -> Settings:
    return Settings()
```

## core/custom_logging.py
```python
import logging

def setup_logging(level: int = logging.INFO):
    logging.basicConfig(level=level, format="%(asctime)s %(levelname)s %(name)s: %(message)s")
    return logging.getLogger()
```

## core/exceptions.py
```python
class AppError(Exception):
    """Base application error."""

class NotFoundError(AppError):
    pass

class ValidationError(AppError):
    pass
```
