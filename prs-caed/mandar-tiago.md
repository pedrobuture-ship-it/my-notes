# mandar tiago

Tiago, vi aqui!

O retorno das rotas do Gestor (tabelaPreco/find e projeto/find) está super leve e rápido.

O problema era que ao entrar no /comprar, o front travava a tela no spinner esperando antes o GET /pais, GET /estado e principalmente o GET /municipio (da api-prscloud, que retorna todos os 5.565 municípios de uma vez, ~441 KB), pra só depois chamar o Gestor e montar os cards de preço.

Bloco 2:
text

Como o Angular guarda essa lista de municípios em memória depois da 1ª chamada, só a primeira abertura ficava lenta (principalmente se a API estivesse fria).

Já ajustei aqui no front pra puxar os preços/projetos do Gestor direto em paralelo ao abrir a tela e carregar os municípios em segundo plano (já que só usa no passo 3 de endereço).