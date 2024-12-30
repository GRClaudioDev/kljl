# Ambiete de desenvolvimetno Laravel

Este repositório foi criado com o intuito de facilitar a creiação de um ambiente básico de desenvolvimento de aplicações em laravel, de acordo com as necessidade do criador.

Este projeto inicia uma instalação do Laravel com Sail, utilizando containers Mysql, Redis, Mailpit e MinIO.

As sessões, cache e filas já são configuradas para o serviço Redis.

Da mesma forma, o stoge padrão já é o S3, emulado no MinIO.

Além dos containers já citados, também foi acrescentado o container PHPMyAdmin, para gerenciamento do Banco de Dados MySQL.

Já vem instalado os pacotes de tradução do Laravel, Laravel Debugbar, LaraDumps, LaraStan, PestPHP.

Os arquivos do Sail foram publicados para permitir o funcionamento mesmo sem as dependências instaladas. Também foi criado um novo script Sail, com comandos personalizados, para aumentar a produtividade.

## Instalação e utilização do Ambiente de Desenvolvimento

O primeiro passo para relizar a utilziação do ambiente de desenvolvimento é realizar o seu clone.

Para isso, no bash, execute o seguinte comando:

```bash
git clone https://github.com/GRClaudioDev/devLaravel.git
```

Em seguida, para para instalar as dependências de desenvolvimento do projeto e iniciar os containers docker, execute o comando a seguir:

```bash
./sail install
```

Este comando irá realizar a criação do arquivo .env, com base no modelo .env.example, iniciar os containers de desenvolvimento, instalar as dependencias de desenvolvimento do composer, criar a chave de criptografia da aplicação Laravel, instalar as dependências de desenvolvimento do node e compilar seus assets.

Caso queira criar o projeto com um novo repositório git, basta fornecer o comando --git junto como o comando de instalação, conforme a seguir:

```bash
./sail install --git
```

Este comando irá fazer todos os comandos de instalação, iniciar um repositório git local, na branch main, e fazer um commit inicial, deixando o ambiente preparado para desenvolvimento.


No comando install pode ser passado um terceiro argumento, que é o nome do repositório no github para sincronizar as alterações. Este comando irá realizar as ações dos comandos anteriores e adicionará o repositório remoto informado no terceiro argumento, já realizando o push do projeto inicial.

Exemplo: Para instalar um projeto com git e repositório remoto git@github.com:GRClaudioDev/devLaravel.git, deve ser executado o seguinte comando:

```bash
./sail install --git git@github.com:GRClaudioDev/devLaravel.git
```

Para evitar chamar o script personalizado sempre com o prefixo ./, pode ser criado um alias no arquivo .bashrc para encurtar o comando. Esse alias também serve para ser utilziado com o comando original do sail, caso o script personalizado não seja encontrado na pasta raiz do sistema, executando o comando ./vendor/bin/sail.

```bash
echo "alias sail='bash $([ -f sail ] && echo sail || echo vendor/bin/sail)'" > ~/.bashrc && source ~/.bashrc
```

Este comando é muito similar ao encontrado na documentação do Larvael, com as seguinte pequenas alterações:

* O comando já cria o alias dentro do arquivo .bashrc;
* Foi alterado o comando para ser executado pelo bash ao invés de utilziar o shell;
* Ao termino da inclusão do alias, o arquivo .bashrc é recarregado.

## Comandos personalizados do sail

EM ELABORAÇÃO

## Licença

Este é um projeto open-source licenciado com a [licença MIT](https://opensource.org/licenses/MIT)