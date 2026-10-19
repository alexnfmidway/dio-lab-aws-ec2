# Laboratório DIO — Gerenciamento de Instâncias Amazon EC2

Projeto desenvolvido para consolidar conhecimentos sobre computação em nuvem e gerenciamento de instâncias utilizando o Amazon EC2, serviço da Amazon Web Services (AWS).

## 🎯 Objetivo

Compreender como criar, configurar, acessar e gerenciar servidores virtuais na AWS, conhecendo os principais componentes de uma instância EC2, as configurações de rede, os controles de segurança e os cuidados necessários para evitar custos inesperados.

## ☁️ O que é Amazon EC2?

O **Amazon EC2 (Elastic Compute Cloud)** é um serviço de computação em nuvem que permite provisionar servidores virtuais sob demanda.

Esses servidores podem hospedar aplicações web, APIs REST, bancos de dados compatíveis com a arquitetura escolhida, serviços de backend e ambientes de desenvolvimento.

Uma das principais vantagens do EC2 é permitir que os recursos computacionais sejam ajustados conforme a necessidade da aplicação, sem exigir a aquisição de um servidor físico.

### Aplicações práticas

- Hospedagem de APIs desenvolvidas em C# e ASP.NET Core.
- Execução de aplicações e serviços de backend.
- Criação de ambientes de homologação e desenvolvimento.
- Implantação de aplicações que precisam de controle sobre o sistema operacional.
- Execução de workloads em infraestrutura configurável na nuvem.

## 🧠 Principais conceitos

| Conceito | Explicação |
|---|---|
| Instância EC2 | Servidor virtual executado na infraestrutura da AWS. |
| AMI | Imagem utilizada como modelo para criar uma instância, contendo o sistema operacional e configurações básicas. |
| Tipo de instância | Define a capacidade de processamento, memória e características de rede. |
| Região | Área geográfica da AWS onde os recursos são provisionados. |
| Zona de disponibilidade | Localização isolada dentro de uma região, utilizada para aumentar a disponibilidade das aplicações. |
| Par de chaves | Mecanismo de autenticação utilizado por determinados métodos de acesso, como SSH em instâncias Linux. |
| Security Group | Firewall virtual que controla o tráfego de entrada e saída da instância. |
| EBS | Serviço de armazenamento em bloco que fornece volumes para instâncias EC2. |
| IP público | Endereço utilizado para comunicação pela internet quando a configuração de rede permite. |
| VPC | Rede virtual isolada na qual os recursos da AWS podem ser implantados. |

## 🧪 Etapas do laboratório

> **Registro da execução:** marque somente as etapas que você realmente realizou. Os campos de configuração devem refletir os valores observados no console da AWS.

### 1. Preparação do ambiente

- [ ] Acessar o console da AWS.
- [ ] Localizar o serviço Amazon EC2.
- [ ] Conferir a região selecionada.
- [ ] Revisar as configurações solicitadas na atividade da DIO.

**Objetivo da etapa:** identificar o ambiente de trabalho e compreender onde os recursos de computação são administrados.

**Registro da execução:** preencher após realizar a etapa.

### 2. Criação e configuração da instância

Durante a criação de uma instância EC2, é necessário selecionar uma imagem de sistema operacional, definir a capacidade computacional e revisar as configurações de armazenamento, rede e segurança.

**Dados da instância**

| Propriedade | Valor observado |
|---|---|
| Nome da instância | Preencher após a criação |
| AMI / sistema operacional | Preencher após a seleção |
| Tipo de instância | Preencher após a seleção |
| Região | Preencher conforme o console |
| Volume EBS / armazenamento | Preencher conforme a configuração |
| Método de acesso | SSH, EC2 Instance Connect ou outro método utilizado |
| Estado da instância | Registrar o estado observado |

**Procedimento geral**

1. Acessar o serviço EC2 no console da AWS.
2. Selecionar a opção para executar uma nova instância.
3. Definir o nome da instância.
4. Selecionar a AMI e o tipo de instância.
5. Configurar o par de chaves, quando necessário.
6. Revisar a VPC, a sub-rede e as regras do Security Group.
7. Conferir o armazenamento e as demais opções.
8. Iniciar a instância e verificar seu estado.

**Resultado observado:** preencher após concluir a criação ou registrar que a etapa ainda não foi executada.

### 3. Rede, segurança e conectividade

O acesso a uma instância depende de mais do que seu estado de execução. É necessário verificar o caminho de rede, as regras de segurança, o endereço utilizado e o método de autenticação.

Pontos importantes:

- O Security Group controla quais conexões podem chegar à instância e quais conexões podem sair.
- Uma conexão SSH com uma instância Linux normalmente utiliza a porta TCP 22.
- Uma aplicação web HTTP geralmente utiliza a porta TCP 80, enquanto HTTPS utiliza a porta TCP 443.
- A abertura de portas não garante conectividade: a VPC, as rotas, a sub-rede e a configuração de endereçamento também precisam permitir o acesso.
- A origem das conexões deve ser limitada ao necessário, evitando exposição desnecessária à internet.

**Checklist de validação**

- [ ] Conferir o estado da instância.
- [ ] Revisar as regras do Security Group.
- [ ] Conferir o endereço e o método de acesso.
- [ ] Testar a conexão conforme as instruções do laboratório.
- [ ] Registrar o resultado do teste.

**Resultado do teste:** preencher com o resultado real, incluindo eventuais erros encontrados e como foram solucionados.

### 4. Ciclo de vida da instância

| Ação | Finalidade | Cuidados |
|---|---|---|
| Iniciar | Coloca uma instância compatível em execução. | Conferir o estado e a conectividade depois da inicialização. |
| Parar | Desliga uma instância compatível sem excluí-la. | Volumes EBS e outros recursos associados podem continuar gerando custos. |
| Reiniciar | Reinicia o sistema operacional da instância. | Não equivale a encerrar e recriar a instância. |
| Encerrar | Finaliza a instância de forma definitiva. | Verificar a proteção contra encerramento e a persistência dos volumes antes de confirmar. |

**Registro da prática:** informar quais ações foram executadas e os estados observados. Não marcar ações que foram apenas estudadas teoricamente.

### 5. Custos e boas práticas

O uso da nuvem exige atenção tanto à segurança quanto ao consumo de recursos.

Boas práticas:

- Selecionar um tipo de instância compatível com a necessidade do exercício.
- Conferir as condições atuais de preços e elegibilidade do AWS Free Tier.
- Parar ou encerrar os recursos quando não forem mais necessários, conforme o objetivo do laboratório.
- Verificar os custos associados a volumes EBS, endereços IPv4 públicos e outros recursos.
- Configurar alertas de orçamento para acompanhar o consumo.
- Aplicar o princípio do menor privilégio nas permissões IAM.
- Restringir as regras de rede ao tráfego necessário.
- Nunca publicar chaves privadas, senhas, tokens ou credenciais no GitHub.

**Atenção:** parar uma instância não significa necessariamente interromper todos os custos relacionados aos recursos associados a ela. Alertas de orçamento também não garantem o desligamento automático dos serviços.

## 📸 Evidências do laboratório

As evidências devem demonstrar as etapas realizadas e os resultados obtidos.

Sugestões de capturas de tela:

1. Console da AWS com a instância criada.
2. Detalhes da instância, incluindo tipo, AMI e estado.
3. Configuração do Security Group.
4. Resultado do teste de acesso, caso realizado.
5. Estado final dos recursos após a prática.

Salve as imagens na pasta `images/` e utilize referências como:

```markdown
![Instância EC2 no console da AWS](images/instancia-ec2.png)
```

Adicione somente imagens reais da execução. Antes de publicar, oculte dados sensíveis, como identificadores de conta, endereços ou informações privadas que não sejam necessários para demonstrar a atividade.

**Evidências adicionadas:** registrar os arquivos de imagem incluídos no repositório.

## 💡 Aprendizados e insights

### 1. O que é possível aprender com o EC2?

O EC2 permite compreender como servidores virtuais são provisionados e administrados na nuvem. A escolha da imagem, do tipo de instância, do armazenamento e da rede influencia a forma como a aplicação será executada.

### 2. Por que a configuração de rede exige atenção?

Uma instância pode estar em execução e ainda assim não aceitar conexões. O acesso depende da combinação entre Security Groups, rotas, sub-redes, endereçamento e autenticação.

### 3. Qual é a importância dos Security Groups?

Eles permitem controlar o tráfego de rede associado às instâncias. Uma configuração adequada reduz a exposição desnecessária e contribui para proteger aplicações e serviços.

### 4. Como evitar custos inesperados?

É importante monitorar os recursos provisionados, verificar as condições de cobrança e conferir os volumes e endereços associados. Os recursos devem ser encerrados ou removidos quando não forem mais necessários, respeitando os requisitos do exercício.

### 5. Como aplicar EC2 em projetos reais?

Em projetos de backend com C# e ASP.NET Core, uma instância EC2 pode hospedar APIs, serviços de integração e aplicações que necessitam de controle sobre o ambiente de execução. Em um cenário de produção, também devem ser considerados monitoramento, atualizações, backups, alta disponibilidade, segurança e automação de implantação.

> Os itens acima apresentam os conceitos que o laboratório permite estudar. Após a execução, complemente esta seção com suas próprias observações e dificuldades encontradas.

## 🚀 Possíveis aplicações profissionais

O conhecimento de EC2 pode ser utilizado em atividades de infraestrutura e implantação de aplicações, incluindo:

- Publicação de APIs REST desenvolvidas em .NET.
- Configuração de ambientes de desenvolvimento e homologação.
- Execução de serviços de backend.
- Integração com outros serviços da AWS.
- Automação de implantação por meio de pipelines CI/CD.
- Monitoramento e diagnóstico de aplicações em execução na nuvem.

## ✅ Conclusão

O gerenciamento de instâncias Amazon EC2 envolve mais do que iniciar um servidor virtual. É necessário compreender a escolha dos recursos computacionais, o armazenamento, a conectividade, os controles de segurança e o ciclo de vida da infraestrutura.

Este repositório organiza os conceitos estudados e oferece uma base de consulta para futuras atividades com computação em nuvem.

**Conclusão da execução prática:** complementar após realizar o laboratório, registrando as etapas concluídas, as evidências coletadas e os principais aprendizados obtidos.

## 📚 Referências

- [Documentação oficial do Amazon EC2](https://docs.aws.amazon.com/ec2/)
- [Guia do usuário do Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html)
- [Documentação oficial de Security Groups](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-security-groups.html)
- [Documentação oficial do AWS Budgets](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html)
- [GitHub Docs — Sintaxe básica de Markdown](https://docs.github.com/pt/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [DIO — GitHub Quick Start](https://github.com/digitalinnovationone/github-quickstart)

---

**Status do projeto:** documentação técnica estruturada. O registro da execução prática e as evidências devem ser atualizados conforme as atividades realmente realizadas no laboratório.
