#Criação de .nuspec

Para a criação do arquivo .nuspec existe dois passos a se seguidos :

1. Criar um projeto de biblioteca de classes.
2. Gerar um manifesto NuSpec no projeto.

#Criar um projeto de biblioteca
*Criar um projeto de biblioteca de classes* Para compartilhar um assembly, inicie com um projeto de biblioteca de classes. O NuGet pode empacotar vários tipos de projetos, mas o caso mais comum ao compartilhar código é usar uma biblioteca de classes. Depois que você criar o pacote, abra o arquivo AssemblyInfo.cs para atualizar os metadados do assembly.

#Criar o arquivo nuspec
*Criar um manifesto NuSpec* O arquivo NuSpec é um manifesto de pacote com metadados importantes sobre o pacote, como autor, descrição e dependências do pacote. O formato do NuSpec é simples de ser criado à mão, mas convém deixar que o comando spec gere o arquivo para você. Execute o comando no mesmo diretório do arquivo de projeto: 

```
nuget spec
```


#Publicando um pacote servidor nuget.org

Depois de criar um pacote, você provavelmente vai querer compartilhá-lo com o mundo. O NuGet.exe possui um comando de publicação exatamente para essa finalidade. Antes de publicar, você precisará criar uma conta em nuget.org.

Quando estiver registrado para uma conta, clique no link da sua conta para ver a sua chave de acesso. Essa chave é importante, pois ela identifica o comando nuget.exe para a galeria e é uma senha irrevogável.

Quando tiver a sua chave, armazene-a em um local seguro usando o seguinte comando:

nuget setApiKey b688a925-0956-40a0-8327-ff2251cf5f9a

Isso feito, use o comando push para publicar o pacote na galeria:

nuget push ProjectName.1.0.0.nupkg

O comando valida a sua chave de API com a galeria, antes de carregar o pacote. Se você criou um pacote de símbolos, conforme discutimos anteriormente, especifique o sinalizador Symbols quando enviar por push o seu pacote:

nuget push ProjectName.1.0.0.nupkg -Symbols

Especifique o nome do pacote principal e não o nome do pacote de símbolos. O comando localiza o pacote de símbolos apropriado por convenção. O comando envia por push o pacote principal para a galeria do NuGet e o pacote de símbolos para o repositório symbolsource.org do parceiro.


#Publicandp um pacote no servidor myget 

Quando estiver registrado para uma conta, clique no link da sua conta para ver a sua chave de acesso. Essa chave é importante, pois ela identifica o comando nuget.exe para a galeria e é uma senha irrevogável.

Quando tiver a sua chave, armazene-a em um local seguro usando o seguinte comando:

nuget push ProjectName.1.0.0.0.nupkg chavedeseguranca -Source https://www.myget.org/F/teste/





