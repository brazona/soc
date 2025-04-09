# Nome do Repositório

__[descrição do repositório: ]__ Repositório template para o padrão das configurações dos diretórios dos projetos, também inclui exemplos de pipeline github actions e documentação de versionamento..

## Versões

__[relação das versões de aplicativos externos: ]__ A aplicação utiliza as seguintes versões:

| Software | Versão |
| --- | --- |
| JDK | 11.0.12 |

## Estrutura do projeto

__[descrição da estrutura do diretório: ]__

``` text

├── .github
│   └── workflows
│       └── script
│           └── manifest.sh
│       └── postgres.yml
│       └── grafana.yml
│       └── deploy.yml
├── app
│   └── grafana
│       └── local
│           └── compose.yaml
│       └── deployment.yaml
│   └── zipkin
│   └── postgres
│   └── grafana
├── docs
│   └── CONTRIBUTING.md
│   └── CODE_OF_CONDUCT.md
│   └── PULL_REQUEST_TEMPLATE.md
└── README.md
```

## Deploy da Aplicação

__[descrição do processo de deploy em ambiente cloud: ]__ O fluxo de trabalho são processos definidos para dar direção a etapa de desenvolvimento , homologação e lançamento.

As alterações são aplicadas em determinado ambiente através das **branchs**, ao publicar uma alteração numa das branchs ***principais*** o pipeline executa a atualização, a tabela abaixo descreve a relação entre branch e o respectivo ambiente:

### Tabela Branch x Ambiente

| Branch | Ambiente |
| --- | --- |
| develop | Aplica no ambiente __DSV__ |
| release/** | Aplica no ambiente __HMG__ |
| pre-release/** | Aplica no ambiente __STG__ |
| main | Aplica no ambiente __PRD__ |

## Execução Local Host

__[descrição do processo de execução da aplicação localhost: ]__ No diretório raiz desse repositório, execute o comando abaixo num termina bash:

``` sh
mvn clean install &&
mvn spring-boot:run
```

Se a instalação ocorrer com sucesso, estará disponível no host: __http://localhost:8080__

## Execução docker compose

__[descrição do processo de execução da aplicação localhost com docker compose: ]__ Para atender a necessidade de executar a os servidore em ambiente local, foi criado um manifesto compose que inicia as configurações iniciais dos servidores, proporcionando os recursos da arquitetura em ambiente **localhost.**

Para executar essa instrução basta abrir o terminal shell, e executar com exemplo abaixo:

```sh
bash app/launch_app.sh grafana-prometheus keycloak postgres
```

Informando ao argumento do arquivo shell, os nomes dos servidores que deseja executar.

> [!NOTE]
> Para executar o comando acima citado, é necessário incluir no diretório **app/**, o arquivo .env, que fornecerá ao docker compose as variáveis de ambiente.
> Procure o arquiteto do projeto e solicite o arquivo **.env**.

## Licença

> [!IMPORTANT]
> *O código fonte neste projeto não possui licença de uso.*

É terminantemente proibido reproduzir, distribuir, alterar, utilizar engenharia reversa ou valer-se de qualquer tentativa de reverter ao seu código-fonte qualquer dos componentes que compõem o SOFTWARE, bem como utilizar subterfúgios para burlar a quantidade de usuários licenciados.
