# S206_pytest

Repositório contendo a aplicação referente ao seminário de Qualidade de Software (2º semestre - 2022).

O pytest é uma ferramenta utilizada para criar e executar testes em python. Sua instalação, aplicação e execução são simples e serão descritas em passos posteriores.

<div align='center'>
<img src='img/pytest_img.png' width=250px></img>
</div>

---
## Clonando projeto
O primeiro passo para executar o projeto é cloná-lo na sua máquina. Para isso, abra o terminal de comando, navegue até o diretório onde deseja alocar o projeto e entre com o seguinte comando:  
```https://github.com/TiagoMPereira/S206_pytest.git```  
Em seguida entre no diretório clonado  
```cd S206_pytest```  

---
## Gerência de dependências
No python a gerência de dependências é feita criando um ambiente virtual e especificando quais pacotes (e quais suas versões) serão utilizados no projeto. Para criar um ambiente virtual basta digitar o seguinte comando no terminal:  
```python -m venv env_projeto```  
Uma vez criado, é preciso ativar o ambiente virtual:  
```env_projeto\Scripts\activate.bat``` (Windows cmd)  
```env_projeto\Scripts\Activate.ps1``` (Windows powershell)  
```env_projeto/bin/activate``` (Linux/MacOS)  

Com o ambiente ativado basta importar as dependências:  
```pip install -r requirements.txt```  
Da mesma forma, é possível gerar o arquivo de dependências com todos os pacotes e versões utilizadas digitando:  
```pip freeze > requirements.txt```  

---
## Instalação
Caso o pytest não esteja nos requisitos instalados pelo requirements.txt é possível instalá-lo a parte.  

```pip install pytest```  


---
## Como usar

1) Crie um arquivo de testes com o prefixo "test_" (Ex.: test_requests.py)  
2) Dentro do arquivo criado, coloque seus casos de teste. Cada caso deve ser uma função nomeada com o prefixo "test_"  
3) Para executar os testes você pode rodar no prompt de comando:  
- ```pytest``` -> para executar todos os testes
- ```pytest -v``` -> para executar os testes detalhadamente
- ```pytest --cov``` -> para gerar o relatório de cobertura de testes

---
## Gerando artefato

Para gerar um artefato de testes, é possível utilizar a biblioteca pytest-hmtl
Para executar e gerar o artefato, basta utilizar os comandos abaixo:
- ```pytest --html=artifact/report.html``` -> para gerar o artefato com a execução dos testes
- ```pytest --cov-report html --cov=tests/ tests/``` -> para gerar relatório de cobertura dos testes


## Comparação com Unittest

| Feature                    | Pytest                             | Unittest                         | Winner   |
|----------------------------|------------------------------------|----------------------------------|----------|
| Installation               | Third Party                        | Built in                         | Unittest |
| Basic Infra                | Can be only a function             | Inheritance                      | Pytest   |
| Basic Assertion            | Builtin assert                     | TestCase instance methods        | Pytest   |
| Flat is better than nested | Function (1 level)                 | Method (2 level)                 | Pytest   |
| Can run each other test    | Can run unittest tests             | Can't pytest test                | Pytest   |
| Test Result on console     | Error Highlight, code snippet      | Only line error, no highlight    | Pytest   |
| Multi param test           | Yes, parametrize, keep flat        | Yes, sub-test, increase nesting  | Pytest   |
| Test setup                 | fixture: module, session, function | Template Method: setup, tearDown | Pytest   |
| Name Refactoring           | poor, because of name conventions  | rich, regular object orientation | Unittest |
| Running Failed Tests       | built in (--lf, --ff)              | your own =,(                     | Pytest   |
| Marks                      | built in                           | your own =,(                     | Pytest   |

source: <https://github.com/renzon/pytest-vs-unittest>