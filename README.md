
## Criando um Copiloto com Fluxo de Conversa Personalizado no Microsoft Copilot Studio

Uma breve descrição sobre o que esse projeto faz e para quem ele é

### Apresentação do Desafio
Como criar um copiloto com Fluxo de conversa personalizado no Microsoft Copilot Studio.

### Pré-requisitos
- Ter acesso a uma conta no Microsoft 365
- Ter um computador

### Etapas do Desafio
- Criando um Copilot em branco
[copilotstudio](https://copilotstudio.microsoft.com)
- Customizar um tópico
- Personalizar uma mensagem de erro de tópico- Aumentas/diminuir a qualidade da resposta com GenAI

### Conteúdo Programático
Criando um Copiloto com fluxo de Conversa Personalizado no Microsoft Copilot Studio
- Apresentação do Desafio
- Criar um Copilot em branco
- Customizar um Tópico
- Personalizar uma mensagem de erro de tópico
- Aumentar/diminuir a qualidade da resposta com GenAI

### Links Úteis
- [Microsoft Learn](https://learn.microsot.com/pt-br/microsoft-copilot-studio)
- [Romão's Learn](https://romaos.com.br/learn)

### Criar um Copilot em branco
- Entre na sua conta do Microsoft 365.
- No site [copilotstudio](https://copilotstudio.microsoft.com/) faça o login.
- Certifique-se de selecionar um ambiente adequado para o novo copilot em branco. Caso seja necessário crie um novo ambiente através do site: [powerApps](https://make.powerapps.com/).
- Selecione a opção "Agentes".
- Nesta janela clique em "Novo agente".
- Atualmente a página do Copilot Studio conta com um suporte IA para auxiliar na criação de agentes personalizados.
- Por via das dúvidas selecione a opção do idioma do agente como  "Inglês (en-US)", visto que os agentes funcionam preferencialmente em com o idioma inglês.

A mensagem padrão que aparece na tela de criação é:

    "Olá! Estou aqui para ajudar a criar um agente para que você consiga fazer mais.
    Você pode dizer algo como "forneça as melhores práticas para gerenciamento de projetos" ou "ajude meus colegas de equipe a integrar um novo projeto".

O que você gostaria de fazer?"

Nosso primeiro é criar um agente em branco. A título de exemplo forneceremos o seguinte comando em resposta a pergunta automática:

    "Eu gostaria de criar um agente chamado "Agente da DIO". Ele deve agir em tom formal com o idioma em português, para retornar informações relevantes da documentação oficial da Microsoft, o Microsoft Learn. Ao retornar uma resposta para a pergunta do usuário ele deve considerar:
    - Buscar a melhor resposta na documentação
    - Retornar a resposta apropriada e amigável de tom formal
    - Retornar uma ou mais citações da documentação"
Após concluir as confirmações clique em "Criar".

Ao fim dessa etapa o agente já terá sido criado e pode ser testado preliminarmente.

### Customizar um Tópico
- Para adicionar um tópico, em “agentes”, vá na aba “Tópicos” e então selecione a opção “Adicionar um tópico”.
- Ao clicar em “Adicionar um tópico” selecione a opção “A partir de um documento em branco”.
- Na janela de “gatilhos”, clique em “editar” para customizar gatilhos.
- Utilize as frases:

        Buscar informações de AI builder.
        O que é AI builder.
        Onde encontre informações da ferramenta de AI da Power Platform.

- Adicione um “novo nó” clicando no “+”.
- Vá em “Avançado” e em seguida em “Respostas generativas”.
Será criada uma nova caixa no fluxograma
- Selecione o input.
- Selecione “Sistema” para escolher as variáveis de sistema.
- Escreva “Activit.Text” e selecione.
Será criada uma nova caixa referente a AI.
- Selecione uma nova mensagem
- Escreva “Tópico de AI Buider encerrado!”.
- Salve as alterações clicando em “salvar”.
Será criada a mensagem de finalização da resposta.

### Personalizar uma mensagem de erro de tópico
#### Primeira opção
Entrar no convesational boosting
Para isso vá em:
- Tópicos
- sistema
- Selecione Conversational Boosting

#### Segunda opção
Entrar no fallback
Para isso vá em:
- Tópicos
- sistema
- Selecione fallback

Na primeira opção:
- No conversational boosting, vá em **"Criar respostas generativas"** e selecione "editar" e desabilite o item:
"Permitir que a inteligencia artificial use o seu conhecimento geral".

- Na conexão **"Todas as outras opções"** adicione o nó **"Enviar uma mensagem"**.

- Escreva a mensagem:

        Olá **NOME DO USUÁRIO**
        Desculpa, mas não foi possível encontrar a resposta que você estava esperando.

        Entre em contato com o suporte para mais informações.
É possível configurar o nome do usuário adicionando uma variável de sistema:

- Clique em **"Inserir variável**
- Depois em **"Sistema"**
- Digite **"User.PrincipalName"**.

