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

