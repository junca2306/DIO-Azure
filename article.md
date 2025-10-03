```markdown
# Azure Open AI na VNet```markdown
# Azure Open AI na VNet

## DEV Community

### Comunidade de desenvolvedores

Um espaço para discutir e acompanhar o desenvolvimento de software e gerenciar sua carreira de software.

---

## Azure Open AI na VNet

Os modelos GPT estão hospedados em vários fornecedores de serviços no momento, e o Microsoft Azure é um deles. Mesmo que os modelos em si sejam os mesmos, existem muitas diferenças, incluindo:

- **custo**
- **funcionalidades**
- **tipo de modelos e versões**
- **localização geográfica**
- **segurança**
- **suporte**
- **etc.**

Um dos aspectos mais importantes quando usamos isso em um Ambiente Empresarial é, claro, a segurança. Ao utilizar os recursos de segurança de rede do Azure com o Azure Open AI, os clientes podem consumir o serviço Open AI de e dentro da VNet, portanto, nenhuma informação está fluindo publicamente.

### Exemplo de Implantação

O repositório de amostras do Azure fornece um arquivo bicep de exemplo para implantar o Azure Open AI em um ambiente VNet.

**GitHub:** [openai-enterprise-iac](https://github.com/Azure-Samples/openai-enterprise-iac)

Os principais recursos que o bicep utiliza são:

- **VNet**
- **Integração VNet para Web App**
- **Endpoint Privado para Azure Open AI**
- **Endpoint Privado para Pesquisa Cognitiva**
- **Zona DNS Privada**

Ao usar esses recursos, todo o tráfego externo do Web App é roteado apenas dentro da VNet e todos os nomes são resolvidos em endereços IP privados. O Open AI e a Pesquisa Cognitiva desligaram o endereço IP público, portanto, não há mais um ponto de interface pública disponível.

### Implantação

O arquivo bicep implantará os seguintes Recursos do Azure. Vamos implantar e confirmar como funciona. Eu crio um grupo de recursos na região East US para meu próprio teste.

```bash
git clone https://github.com/Azure-Samples/openai-enterprise-iac
cd openai-enterprise-iac
az group create -n openaitest -l eastus
az deployment group create -g openaitest -f .\infra\main.bicep
```

Uma vez que eu execute o comando acima, vejo que a implantação foi iniciada. Aguarde até que a implantação seja concluída.

### Teste

Vamos ver se a implantação foi bem-sucedida.

#### Azure Open AI

Vamos tentar o acesso público primeiro. Eu poderia criar uma implantação sem nenhum problema. Mas ao tentar no playground de Chat em meu Portal do Azure, vejo o seguinte erro.

#### E quanto ao acesso via API Web?

De uma ferramenta avançada do App Service, eu login na sessão Bash e primeiro faço um ping na URL do serviço. Vejo que o endereço IP privado atribuído ao Endpoint Privado é retornado. Depois, uso o comando curl para enviar a solicitação para o endpoint.

---

**Comentários Principais**

(0)

**Assinar**

---

### Mais sobre Kenichiro Nakamura

Kenichiro Nakamura é um usuário confiável e membro da comunidade desde 3 de fevereiro de 2018.

#### Outros Posts

- **Azure ML Prompt flow: Use content safety antes de enviar uma solicitação ao LLM**
- **C#: Azure Open AI e Chamada de Função**

---

**Apoio da Comunidade DEV**

Obrigado aos nossos patrocinadores Diamond por apoiarem a DEV Community.
```

```markdown
# Azure Open AI na VNet

## DEV Community

### Comunidade de desenvolvedores

Um espaço para discutir e acompanhar o desenvolvimento de software e gerenciar sua carreira de software.

---

## Azure Open AI na VNet

Os modelos GPT estão hospedados em vários fornecedores de serviços no momento, e o Microsoft Azure é um deles. Mesmo que os modelos em si sejam os mesmos, existem muitas diferenças, incluindo:

- **custo**
- **funcionalidades**
- **tipo de modelos e versões**
- **localização geográfica**
- **segurança**
- **suporte**
- **etc.**

Um dos aspectos mais importantes quando usamos isso em um Ambiente Empresarial é, claro, a segurança. Ao utilizar os recursos de segurança de rede do Azure com o Azure Open AI, os clientes podem consumir o serviço Open AI de e dentro da VNet, portanto, nenhuma informação está fluindo publicamente.

### Exemplo de Implantação

O repositório de amostras do Azure fornece um arquivo bicep de exemplo para implantar o Azure Open AI em um ambiente VNet.

**GitHub:** [openai-enterprise-iac](https://github.com/Azure-Samples/openai-enterprise-iac)

Os principais recursos que o bicep utiliza são:

- **VNet**
- **Integração VNet para Web App**
- **Endpoint Privado para Azure Open AI**
- **Endpoint Privado para Pesquisa Cognitiva**
- **Zona DNS Privada**

Ao usar esses recursos, todo o tráfego externo do Web App é roteado apenas dentro da VNet e todos os nomes são resolvidos em endereços IP privados. O Open AI e a Pesquisa Cognitiva desligaram o endereço IP público, portanto, não há mais um ponto de interface pública disponível.

### Implantação

O arquivo bicep implantará os seguintes Recursos do Azure. Vamos implantar e confirmar como funciona. Eu crio um grupo de recursos na região East US para meu próprio teste.

```bash
git clone https://github.com/Azure-Samples/openai-enterprise-iac
cd openai-enterprise-iac
az group create -n openaitest -l eastus
az deployment group create -g openaitest -f .\infra\main.bicep
```

Uma vez que eu execute o comando acima, vejo que a implantação foi iniciada. Aguarde até que a implantação seja concluída.

### Teste

Vamos ver se a implantação foi bem-sucedida.

#### Azure Open AI

Vamos tentar o acesso público primeiro. Eu poderia criar uma implantação sem nenhum problema. Mas ao tentar no playground de Chat em meu Portal do Azure, vejo o seguinte erro.

#### E quanto ao acesso via API Web?

De uma ferramenta avançada do App Service, eu login na sessão Bash e primeiro faço um ping na URL do serviço. Vejo que o endereço IP privado atribuído ao Endpoint Privado é retornado. Depois, uso o comando curl para enviar a solicitação para o endpoint.

---

**Comentários Principais**

(0)

**Assinar**

---

### Mais sobre Kenichiro Nakamura

Kenichiro Nakamura é um usuário confiável e membro da comunidade desde 3 de fevereiro de 2018.

#### Outros Posts

- **Azure ML Prompt flow: Use content safety antes de enviar uma solicitação ao LLM**
- **C#: Azure Open AI e Chamada de Função**

---

**Apoio da Comunidade DEV**

Obrigado aos nossos patrocinadores Diamond por apoiarem a DEV Community.
```


## DEV Community

### Comunidade de desenvolvedores

Um espaço para discutir e acompanhar o desenvolvimento de software e gerenciar sua carreira de software.

---

## Azure Open AI na VNet

Os modelos GPT estão hospedados em vários fornecedores de serviços no momento, e o Microsoft Azure é um deles. Mesmo que os modelos em si sejam os mesmos, existem muitas diferenças, incluindo:

- **custo**
- **funcionalidades**
- **tipo de modelos e versões**
- **localização geográfica**
- **segurança**
- **suporte**
- **etc.**

Um dos aspectos mais importantes quando usamos isso em um Ambiente Empresarial é, claro, a segurança. Ao utilizar os recursos de segurança de rede do Azure com o Azure Open AI, os clientes podem consumir o serviço Open AI de e dentro da VNet, portanto, nenhuma informação está fluindo publicamente.

### Exemplo de Implantação

O repositório de amostras do Azure fornece um arquivo bicep de exemplo para implantar o Azure Open AI em um ambiente VNet.

**GitHub:** [openai-enterprise-iac](https://github.com/Azure-Samples/openai-enterprise-iac)

Os principais recursos que o bicep utiliza são:

- **VNet**
- **Integração VNet para Web App**
- **Endpoint Privado para Azure Open AI**
- **Endpoint Privado para Pesquisa Cognitiva**
- **Zona DNS Privada**

Ao usar esses recursos, todo o tráfego externo do Web App é roteado apenas dentro da VNet e todos os nomes são resolvidos em endereços IP privados. O Open AI e a Pesquisa Cognitiva desligaram o endereço IP público, portanto, não há mais um ponto de interface pública disponível.

### Implantação

O arquivo bicep implantará os seguintes Recursos do Azure. Vamos implantar e confirmar como funciona. Eu crio um grupo de recursos na região East US para meu próprio teste.

```bash
git clone https://github.com/Azure-Samples/openai-enterprise-iac
cd openai-enterprise-iac
az group create -n openaitest -l eastus
az deployment group create -g openaitest -f .\infra\main.bicep
```

Uma vez que eu execute o comando acima, vejo que a implantação foi iniciada. Aguarde até que a implantação seja concluída.

### Teste

Vamos ver se a implantação foi bem-sucedida.

#### Azure Open AI

Vamos tentar o acesso público primeiro. Eu poderia criar uma implantação sem nenhum problema. Mas ao tentar no playground de Chat em meu Portal do Azure, vejo o seguinte erro.

#### E quanto ao acesso via API Web?

De uma ferramenta avançada do App Service, eu login na sessão Bash e primeiro faço um ping na URL do serviço. Vejo que o endereço IP privado atribuído ao Endpoint Privado é retornado. Depois, uso o comando curl para enviar a solicitação para o endpoint.

---

**Comentários Principais**

(0)

**Assinar**

---

### Mais sobre Kenichiro Nakamura

Kenichiro Nakamura é um usuário confiável e membro da comunidade desde 3 de fevereiro de 2018.

#### Outros Posts

- **Azure ML Prompt flow: Use content safety antes de enviar uma solicitação ao LLM**
- **C#: Azure Open AI e Chamada de Função**

---

**Apoio da Comunidade DEV**

Obrigado aos nossos patrocinadores Diamond por apoiarem a DEV Community.
```

```markdown
# Azure Open AI na VNet

## DEV Community

### Comunidade de desenvolvedores

Um espaço para discutir e acompanhar o desenvolvimento de software e gerenciar sua carreira de software.

---

## Azure Open AI na VNet

Os modelos GPT estão hospedados em vários fornecedores de serviços no momento, e o Microsoft Azure é um deles. Mesmo que os modelos em si sejam os mesmos, existem muitas diferenças, incluindo:

- **custo**
- **funcionalidades**
- **tipo de modelos e versões**
- **localização geográfica**
- **segurança**
- **suporte**
- **etc.**

Um dos aspectos mais importantes quando usamos isso em um Ambiente Empresarial é, claro, a segurança. Ao utilizar os recursos de segurança de rede do Azure com o Azure Open AI, os clientes podem consumir o serviço Open AI de e dentro da VNet, portanto, nenhuma informação está fluindo publicamente.

### Exemplo de Implantação

O repositório de amostras do Azure fornece um arquivo bicep de exemplo para implantar o Azure Open AI em um ambiente VNet.

**GitHub:** [openai-enterprise-iac](https://github.com/Azure-Samples/openai-enterprise-iac)

Os principais recursos que o bicep utiliza são:

- **VNet**
- **Integração VNet para Web App**
- **Endpoint Privado para Azure Open AI**
- **Endpoint Privado para Pesquisa Cognitiva**
- **Zona DNS Privada**

Ao usar esses recursos, todo o tráfego externo do Web App é roteado apenas dentro da VNet e todos os nomes são resolvidos em endereços IP privados. O Open AI e a Pesquisa Cognitiva desligaram o endereço IP público, portanto, não há mais um ponto de interface pública disponível.

### Implantação

O arquivo bicep implantará os seguintes Recursos do Azure. Vamos implantar e confirmar como funciona. Eu crio um grupo de recursos na região East US para meu próprio teste.

```bash
git clone https://github.com/Azure-Samples/openai-enterprise-iac
cd openai-enterprise-iac
az group create -n openaitest -l eastus
az deployment group create -g openaitest -f .\infra\main.bicep
```

Uma vez que eu execute o comando acima, vejo que a implantação foi iniciada. Aguarde até que a implantação seja concluída.

### Teste

Vamos ver se a implantação foi bem-sucedida.

#### Azure Open AI

Vamos tentar o acesso público primeiro. Eu poderia criar uma implantação sem nenhum problema. Mas ao tentar no playground de Chat em meu Portal do Azure, vejo o seguinte erro.

#### E quanto ao acesso via API Web?

De uma ferramenta avançada do App Service, eu login na sessão Bash e primeiro faço um ping na URL do serviço. Vejo que o endereço IP privado atribuído ao Endpoint Privado é retornado. Depois, uso o comando curl para enviar a solicitação para o endpoint.

---

**Comentários Principais**

(0)

**Assinar**

---

### Mais sobre Kenichiro Nakamura

Kenichiro Nakamura é um usuário confiável e membro da comunidade desde 3 de fevereiro de 2018.

#### Outros Posts

- **Azure ML Prompt flow: Use content safety antes de enviar uma solicitação ao LLM**
- **C#: Azure Open AI e Chamada de Função**

---

**Apoio da Comunidade DEV**

Obrigado aos nossos patrocinadores Diamond por apoiarem a DEV Community.
```
