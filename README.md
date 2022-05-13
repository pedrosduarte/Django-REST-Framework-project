# Atividade prática de Python/Django/DRF - Polícia Civil do Ceará

Repositório da atividade prática referente ao processo seletivo de Pessoa Desenvolvedora Python júnior.

## Instruções de inicialização

-   Clonar esse repositório para a máquina local (`git clone`);
-   Na pasta local do repositório, criar um ambiente virtual (`python -m venv venv`) e ativá-lo (`source venv/bin/activate` em Linux);
-   Instalar as dependências do arquivo requirements.txt (`pip install -r requirements.txt`);
-   Executar as migrações do banco de dados (`python manage.py migrate`);
-   Executar o comando especial para o preenchimento inicial dos dados (`python manage.py preencherdb`);
-   Iniciar o servidor (`python manage.py runserver`).

## Endpoints da API

Todos os endpoints do projeto foram desenvolvidos usando [`ModelViewSets`](https://www.django-rest-framework.org/api-guide/viewsets/#modelviewset), com a exceção do objeto `Objeto`, que utiliza um [`ReadOnlyModelViewset`](https://www.django-rest-framework.org/api-guide/viewsets/#readonlymodelviewset). Os `ModelViewSets` são capazes de executar as seguintes ações:

-   `GET`: Retorna um JSON com todos os objetos registrados no banco dados, ou um objeto específico, se sua chave primária for passada na URL;
-   `POST`: Cria um novo objeto com os dados passados no request;
-   `PATCH`: Atualiza um ou vários campos de um objeto específico, passados no request;
-   `DELETE`: Apaga uma instância de um objeto específico.

Já o `ReadOnlyModelViewset` suporta apenas as ações do método `GET`, isto é, ele só gera endpoints de leitura de dados. <br>
Dessa forma, essa API conta com os seguintes endpoints:

-   `/api/armas/` - ModelViewSet
-   `/api/calibres/` - ModelViewSet
-   `/api/municoes/` - ModelViewSet
-   `/api/objetos/` - ReadOnlyModelViewset
-   `/api/tipos_objetos/` - ModelViewSet
