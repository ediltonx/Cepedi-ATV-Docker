# Projéto prático de Docker

## Nesta atividade, você deverá configurar e subir uma infraestrutura completa de uma aplicação web full-stack utilizando Docker. A aplicação é composta por um backend em Python/Flask que se comunica com um banco de dados MySQL, e um frontend que será servido pelo Nginx.

## Descrição do Cenário

A aplicação foi desenvolvida utilizando a seguinte stack de tecnologias:

Flask (Python): O backend foi implementado utilizando Flask, um microframework para desenvolvimento de aplicações web em Python. Ele é responsável por fornecer a API REST que será consumida pelo frontend.
MySQL 8.0: O banco de dados utilizado é o MySQL, responsável pelo armazenamento das informações da aplicação (usuários com nome e idade).
Nginx: O frontend da aplicação é servido pelo Nginx, um servidor web que será utilizado para servir arquivos estáticos (HTML, CSS e JavaScript) e atuar como proxy reverso para a API do backend.
Docker: Toda a infraestrutura será containerizada utilizando Docker, garantindo que todos os componentes da aplicação sejam isolados e reproduzíveis em qualquer ambiente.

## Comunicação entre o Frontend e o Backend

A comunicação entre o frontend (Nginx) e o backend (Flask) será feita da seguinte maneira:

O Nginx será configurado como um proxy reverso, o que significa que ele receberá as requisições HTTP dos clientes e redirecionará as chamadas para o backend.
Sempre que o frontend fizer uma chamada para /api, o Nginx encaminhará a requisição para o backend Flask que está rodando na porta 5000.
As requisições do frontend, como criação e listagem de usuários, serão redirecionadas para o backend que processa a requisição e interage com o banco de dados MySQL. O backend então retorna a resposta ao Nginx, que a envia de volta para o cliente no navegador.
Comunicação:

O cliente acessa a aplicação frontend em http://localhost:80.
O frontend envia uma requisição para listar os usuários em http://localhost/api/users.
O Nginx intercepta essa requisição e a redireciona para http://backend:5000/api/users.
O backend processa a requisição e retorna os dados dos usuários, que são exibidos no frontend.
O arquivo nginx.conf já foi fornecido, de forma que o nginx já deverá atuar para fazer essa comunicação, além disso, no frontend (main.js) existe uma variável denominada apiUrl que faz o mapeamento para /api/users.
