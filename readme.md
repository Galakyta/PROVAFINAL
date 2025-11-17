

Documentação técnica do projeto da API de micro gestão para centros
comerciais
Título do Projeto:API Andertech - Micro Gestão financeira empresarial
Grupo: Giuseppe Trinco Nichele // Marcos Vinicius Da Rocha Schiavon Ferreira
1. Objetivo do Projeto integrar a api com o programa de forma que ela consiga dar um relatorio final com as necessidades da gestao
2. estrutura da solução - foram criadas algumas novas rotas e um model novo exclusivamente para as despesas
2.2 - Integração da API com a Solução / foram cridas novas rotas get para isso, e uma funcao nova para retornar no hmtml
3 - ENDPOINTS DA API
a separação das rotas foi feito por funcionalidade, seguindo o padrão REST, elas seguem com abaixo com suas
implementações:
[GET] [/Despesas] [Retornando todos os dispositivos cadastrados]
[GET] [/Despesas/{id}] [Retornando todos os dispositivos cadastrados]
[POST] [/Despesas] [Cadastrar um novo dispositivo]
[PUT] [/Despesas] [Atualiza os dados de um dispesa]
[DELETE] [/Despesas}] [Remover uma dispesa do banco de dados]
4 - Organização do Código
como o projeto teve seu foco em modularidade e clareza, mantivemos uma separação clara entre as camadas
de dados, domínio e rotas
Models/Dispositivo.CS define a estrutura da entidade principal juntamente ao enum
Models/AppDbContext.cs é responsável pela configuração do banco de dados SQLite e mapeamento
Rotas/Rota_GET.cs implementa as operações de listagem e consulta por ID
Rotas/Rota_POST.cs gerencia o cadastro de novos dispositivos
Rotas/Rota_PUT.cs implementa a atualização de registros existentes
Rotas/Rota_DELETE.cs gerencia a exclusão de dispositivos do banco
Program/cs é o arquivo principal que inicializa a aplicação
5 - justificativas técnicas
a ideia central do codigo foi simples, manter o codigo original intacto e auditavel permitindo expandir a forma final do codigo
