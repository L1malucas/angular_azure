# Readme - Tutorial Azure Static Web Apps com Angular

Este é um breve guia de utilização do Azure Static Web Apps para implantar um aplicativo Angular seguindo os passos do tutorial fornecido por Marco Venturi no FreeCodeCamp.org.

Título do Tutorial: How to Use Azure Static Web Apps to Deploy an Angular App

Autor: Marco Venturi
## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes requisitos instalados e configurados:

- Conta no GitHub
- Node.js (disponível para download [aqui](https://nodejs.org/))
- Npm (gerenciador de pacotes Node.js, incluído na instalação do Node)
- Angular CLI (interface de linha de comando para criar, desenvolver e manter seu aplicativo Angular, disponível para download [aqui](https://cli.angular.io/))
- Conta Azure (você pode iniciar gratuitamente criando sua conta [aqui](https://azure.microsoft.com/pt-br/free/). Após o término do período de avaliação gratuita, verifique os custos incorridos. As tecnologias em nuvem são poderosas e podem facilitar sua vida, mas também podem ser caras se não forem bem gerenciadas.)

Certifique-se de ter todas essas ferramentas configuradas antes de prosseguir com o tutorial.
### Versões Usadas
    - Angular 16
    - Node.js 16
## O que vamos construir - Visão Geral

Neste tutorial, criaremos um aplicativo Angular localmente e o implantaremos usando o Azure Static Web Apps. Vamos criar um repositório no GitHub especificamente para este projeto.

O repositório terá duas branches: "main" e "develop". Vamos criar um aplicativo web estático no Azure e conectá-lo à branch "main" do repositório.

De volta ao seu computador, você editará o código e o enviará para a branch "develop". Em seguida, você mesclará a branch "develop" com a branch "main" e verá a nova versão do seu aplicativo online.
Aqui estão os passos principais:

    Criar o aplicativo Angular localmente usando o Angular CLI.
    Executar o comando ng build para gerar os arquivos de build.
    Remover a pasta dist do arquivo .gitignore.
    Configurar o Azure Static Web Apps:
        Selecionar o repositório do GitHub para implantação.
        Definir o tipo de pré-build como "Angular".
        Especificar o diretório raiz (root) e o diretório de saída do aplicativo (dist/app).
        Criar o Static Web App no Azure.

## Passo 1 - Criar o Aplicativo Angular Localmente

Primeiro, crie um diretório específico em seu computador e navegue até ele. No terminal, digite:

```bash
mkdir angular_azure
cd angular_azure
```

Dentro do diretório, crie um novo aplicativo Angular chamado "angular_app":

```bash
ng new angular_app
```

Faça  build da aplicação com o comando:
```bash
ng build
```

O Angular CLI fará algumas perguntas. Escolha as opções desejadas e verifique se o aplicativo está funcionando corretamente executando o comando:

```bash
ng serve --open
```

Certifique-se de que o aplicativo esteja sendo executado corretamente e, em seguida, pare a execução (Ctrl + C).

## Passo 2 - Enviar o Aplicativo Angular para o Repositório do GitHub

Certifique-se de ter criado um novo repositório no GitHub para este projeto. Se você não souber como criar um novo repositório, pode obter mais informações [aqui](https://docs.github.com/pt/github/getting-started-with-github/create-a-repo).

Uma vez que o repositório esteja pronto, envie o aplicativo Angular do seu computador para o repositório. Use os seguintes comandos:

```bash
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/<REPO>.git
git push -u origin main
```

Certifique-se de substituir `<REPO>` pela URL do seu repositório. Após executar esses comandos com sucesso, você verá uma confirmação do envio.

## Passo 3 - Configurar o Azure

Agora vamos configurar o Azure Static Web Apps para implantar o aplicativo Angular.

1. Acesse o portal do Azure [aqui](https://portal.azure.com/) e faça login na sua conta.
2. Navegue até o grupo de recursos desejado.
3. Clique em "Criar um recurso" e pesquise por "Static Web App".
4. Selecione "Static Web App" na lista de recursos disponíveis.

Configurando as opções do Azure Static Web Apps:

- **Assinatura e Grupo de Recursos**: Escolha a assinatura e o grupo de recursos adequados.
- **Detalhes do aplicativo**: Escolha um nome para o aplicativo, por exemplo, "angular-app".
- **Plano de hospedagem**: Selecione o plano "Free" (gratuito).
- **Localização**: Escolha a região adequada para a implantação do aplicativo.

Agora, vamos definir algumas informações específicas do aplicativo:

- **Detalhes de compilação**:
    - **Fonte de compilação**: Selecione o repositório do GitHub onde você enviou o código do aplicativo.
    - **Preset de compilação**: Escolha "Angular" como o preset de compilação.
    - **Local do aplicativo**: Defina o caminho raiz do aplicativo como "/".
    - **Local de saída**: Defina o local de saída como "dist/app".

Por fim, clique em "Criar" para criar o Static Web App no Azure.

Aguarde alguns instantes enquanto o Azure cria o Static Web App. Após a conclusão, você terá uma visão geral do aplicativo criado.

Parabéns! Você concluiu com sucesso a configuração do Azure Static Web Apps para implantar o aplicativo Angular.

## Passo 4 - Implantação do Aplicativo

Agora que o Azure Static Web App está configurado, o processo de implantação do aplicativo Angular será automático. Após cada push para a branch principal do repositório no GitHub, o Azure realizará o build e a implantação do aplicativo.

Acesse o URL fornecido na visão geral do Static Web App para ver seu aplicativo implantado.

## Passo 5 - Criar uma Nova Branch

Volte para o seu repositório local e crie a branch "develop":

```bash
git checkout -b develop
```

Em seguida, edite o arquivo `src/app/app.component.html` como desejado e envie a nova branch para o repositório remoto:

```bash
git push origin develop
```

## Passo 6 - Mesclar as Branches

Agora que a branch "develop" contém as alterações, você precisa mesclá-la à branch "main" para que as mudanças sejam refletidas no aplicativo online.

Crie uma solicitação pull no GitHub e realize a mesclagem. Após a mesclagem, aguarde alguns minutos para ver a nova versão do aplicativo online.

Parabéns! Você concluiu com sucesso o tutorial Azure Static Web Apps com Angular.
