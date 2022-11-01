
# Projeto Python com FastAPI

![alt text](https://github.com/HenriqueHideaki/PythonFastApi/blob/main/FastApi.png)

FastAPI é um framework web moderno e rápido (de alto desempenho) para construir APIs com Python 3.7+ baseado em dicas de tipo Python padrão..

[FastAPILink](https://fastapi.tiangolo.com/)

## Dependências
- Docker
- Docker Compose
- Pipenv
- Postgres
- API MercadoBitcoin

## Preparando o ambiente de desenvolvimento

Usando o gerenciador de pacostes [pip](https://pip.pypa.io/en/stable/).

```bash
pip install pipenv
```
```bash
pipenv shell
```
```bash
pipenv install fastapi
```
```bash
pipenv install "uvicorn[standard]"
```

Obs: Selecionar o interpretador Python correto do seu ambiente virtual

## Criação

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

## Rodando o servidor

```bash
$uvicorn main:app --port 8080 --reload

INFO:     Uvicorn running on http://127.0.0.1:8000 (Press CTRL+C to quit)
INFO:     Started reloader process [28720]
INFO:     Started server process [28722]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
```

## Verifique
Abra seu navegador em http://127.0.0.1:8000/items/5?q=somequery.

Você verá a resposta JSON como:
```Json
{"item_id": 5, "q": "somequery"}
```
Você acabou de criar uma API que:
- [x] Recebe requisições HTTP nas rotas / e /items/{item_id}.
- [x] Ambas rotas fazem operações GET (também conhecido como métodos HTTP).
- [x] A rota /items/{item_id} tem um parâmetro de rota item_id que deve ser um int.
- [x] A rota /items/{item_id} tem um parâmetro query q str opcional.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
