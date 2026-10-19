# Laboratório DIO — Gerenciamento de Instâncias Amazon EC2

> Projeto de estudo desenvolvido para documentar os conceitos e as práticas do laboratório de gerenciamento de instâncias EC2 da AWS.

## 🎯 Objetivo

Consolidar os conhecimentos sobre o Amazon EC2 (Elastic Compute Cloud), registrar as etapas realizadas durante o laboratório e manter um material de consulta para estudos futuros.

## ☁️ O que é Amazon EC2?

O Amazon EC2 é um serviço da AWS que permite provisionar servidores virtuais na nuvem. Uma instância EC2 pode executar aplicações, APIs, sites, serviços e ambientes de desenvolvimento, de acordo com o sistema operacional e os recursos escolhidos.

## 🧠 Conceitos importantes

| Conceito | Explicação |
|---|---|
| Instância | Servidor virtual executado na AWS. |
| AMI | Imagem usada como modelo para iniciar uma instância, incluindo o sistema operacional e as configurações básicas. |
| Tipo de instância | Define os recursos de computação, memória, armazenamento e rede disponíveis. |
| Região e zona de disponibilidade | A região é uma área geográfica da AWS; as zonas são locais isolados dentro de uma região. |
| Par de chaves | Permite autenticação segura em métodos compatíveis, como SSH em instâncias Linux. A chave privada deve ser protegida. |
| Security Group | Firewall virtual que controla o tráfego de entrada e saída da instância. |
| EBS | Serviço de armazenamento em bloco que pode ser associado a instâncias EC2. |
| IP público | Endereço que pode permitir acesso pela internet, dependendo da configuração de rede e das regras de segurança. |

## 🧪 Roteiro do laboratório

> Preencha esta seção com o que você realmente executou nas aulas. Não marque etapas como concluídas sem ter realizado ou verificado a ação.

### 1. Preparação

- [ ] Acessei o console da AWS.
- [ ] Conferi a região selecionada.
- [ ] Revisei os requisitos e as configurações propostas na aula.

**Anotações:**  
_Adicione aqui observações sobre a preparação do ambiente._

### 2. Criação da instância

Registre os valores utilizados durante a prática:

- **Nome da instância:** `PREENCHER`
- **AMI / sistema operacional:** `PREENCHER`
- **Tipo de instância:** `PREENCHER`
- **Região:** `PREENCHER`
- **Armazenamento configurado:** `PREENCHER`
- **Método de acesso:** `PREENCHER`

Passos gerais no console:

1. Abrir o serviço **EC2**.
2. Selecionar **Launch instance / Executar instância**.
3. Definir um nome e escolher uma AMI.
4. Selecionar um tipo de instância compatível com o laboratório.
5. Configurar o par de chaves, a rede e o Security Group.
6. Revisar as opções e iniciar a instância.
7. Conferir o estado e os detalhes da instância.

### 3. Acesso e conectividade

- [ ] Verifiquei o estado da instância.
- [ ] Revisei as regras do Security Group.
- [ ] Testei o método de acesso demonstrado na aula.
- [ ] Registrei o resultado do teste.

**Resultado observado:** `PREENCHER`

**Importante:** não abra portas para `0.0.0.0/0` sem necessidade. Para SSH (porta 22), restrinja a origem ao seu IP sempre que possível. Não publique chaves privadas, senhas, tokens, IDs de conta ou outros dados sensíveis em capturas de tela.

### 4. Ciclo de vida da instância

| Ação | Para que serve | Observação |
|---|---|---|
| Iniciar | Liga uma instância parada. | Confira o estado após a ação. |
| Parar | Desliga uma instância compatível, mantendo seus recursos persistentes conforme a configuração. | O armazenamento e outros recursos podem continuar gerando custos. |
| Reiniciar | Reinicia o sistema operacional da instância. | Não é a mesma coisa que encerrar. |
| Encerrar | Finaliza a instância. | É uma ação potencialmente irreversível; confira a proteção contra encerramento e o comportamento dos volumes antes de confirmar. |

**Ações praticadas e resultados:** `PREENCHER`

### 5. Custos e boas práticas

- Escolha o tipo de instância de acordo com a necessidade do laboratório.
- Confira os preços e as condições atuais do AWS Free Tier antes de iniciar recursos.
- Pare ou encerre os recursos quando não forem mais necessários, conforme o objetivo do exercício.
- Verifique volumes EBS, endereços IP públicos e outros recursos associados: alguns podem gerar cobrança mesmo quando a instância está parada.
- Configure alertas de orçamento quando apropriado. Eles ajudam a monitorar gastos, mas não garantem a interrupção automática de recursos.
- Aplique o princípio do menor privilégio em IAM e nas regras de rede.
- Nunca envie credenciais ou chaves privadas para o GitHub.

## 📸 Evidências da prática

Adicione capturas de tela na pasta `images/` e faça referência a elas aqui. Remova ou oculte dados sensíveis antes de publicar.

Exemplo, depois de adicionar a imagem:

```markdown
![Instância no console EC2](images/instancia-ec2.png)
```

**Evidências adicionadas:** `PREENCHER`

## 💡 Aprendizados e insights

Complete após realizar o laboratório:

1. **O que aprendi:** `PREENCHER`
2. **Qual etapa exigiu mais atenção:** `PREENCHER`
3. **Como a configuração de rede influencia o acesso:** `PREENCHER`
4. **Quais cuidados ajudam a evitar custos inesperados:** `PREENCHER`
5. **Como posso aplicar EC2 em um projeto real:** `PREENCHER`

## ✅ Conclusão

Este repositório serve como registro de estudo sobre o gerenciamento de instâncias Amazon EC2. A conclusão final deve resumir as etapas realmente executadas, os resultados observados e os principais aprendizados obtidos durante as aulas.

## 📚 Referências

- [Amazon EC2 — documentação oficial da AWS](https://docs.aws.amazon.com/ec2/)
- [Gerenciamento de instâncias EC2 — material indicado no desafio](https://docs.aws.amazon.com/pt_br/toolkit-for-visual-studio/latest/user-guide/tkv-ec2-ami.html)
- [GitHub Docs — formatação Markdown](https://docs.github.com/pt/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [GitHub Quick Start da DIO](https://github.com/digitalinnovationone/github-quickstart)

---

**Status do projeto:** documentação inicial criada; atualize os campos `PREENCHER` e as caixas de seleção com base na prática realizada.
