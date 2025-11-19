NOME DA DUPLA: 

MARCOS VINICIUS DA ROCHA SCHIAVON FERREIRA
GIUSEPPE TRINCO NICHELE

dependencias:
dotnet tool install --global dotnet-ef
.NET 7.0.2



a ideia do projeto foi permitir que o contratante da nossa api conseguisse ter um relatorio final dos gastos não só
com os dispositivos diversos que ele poderia ter incluido na api, mas disponibilizar um relatorio da receita com os custos EM TORNO
de manter as maquinas funcionando, pois nesse tipo de negocio, a maior parte dos seus gastos vão ser apenas a 
manutenção das maquinas, por isso a gente decidiu focar nisso como dupla.

varias rotas novas foram implementadass e uma extra pro propio relatorio, foi mantido exatamente o mesmo modelo das outras enquanto o projeto foi desenvolvido para manter elas relativamente iguais e padronizadas pra caso seja preciso alterar ou adicionar novas rotas no futuro


O MOTIVO DO CODIGO NN RODAR NA SALA DURANTE A PROVA:

https://api.nuget.org/v3/index.json


O codigo quebrou de forma randomica durante o dessenvolvimento na prova, quase todas as dependencias do codigo precisam acessar esse index.json do nuget, oque gerou o erro fatal foi o restore que o dotnet run faz implicitamente que tenta puxar as dependendicas desse endereço, como o projeto foi clonado e executado antes da prova começar ele inicialmente funcionou como deveria pelos arquivo que foram deixados no cache nesse momento, como parte dos arquivos da dependencia etavam no pc metade do codigo rodou sem problemas, mas conforme mais funçoes foram adicionadas o dotnet precisou puxar o restore e levando o codigo a quebrar pela falta do index, tanto que o erro em si foi de build e não compilação.

agora o codigo foi tratado com o comando dotnet publish -c Release -o publish, que justamente baixa as dependencias e gera um arquivo    
.ddl que funciona mesmo sem acesso ao nuget por deixar as dependencias na nova pasta publish, mas o programa ainda precisa do dotnet funcionando. Mas CASO o nuget não consiga ser alcançado ele usa os arquivos
na pasta publish, posibilitando executar o programa por dotnet prototipoGestao.dll no terminal.


TLDR:
se o dotnet run nn funcionar pq deu erro do index.json roda com esse comando que agora ele tem as dependencias direto no projeto

cd publish
dotnet prototipoGestao.dll

