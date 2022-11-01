
# Projeto Python com Fast API

FastAPI é um framework web moderno e rápido (de alto desempenho) para construir APIs com Python 3.7+ baseado em dicas de tipo Python padrão..

[FastAPILink](https://fastapi.tiangolo.com/)

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install FastAPI.

```bash
pip install fastapi
```
```bash
pip install "uvicorn[standard]"
```

## Usage

```python
import foobar

from typing import Union

from fastapi import FastAPI

app = FastAPI()


@app.get("/")
def read_root():
    return {"Hello": "World"}


@app.get("/items/{item_id}")
def read_item(item_id: int, q: Union[str, None] = None):
    return {"item_id": item_id, "q": q}
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
