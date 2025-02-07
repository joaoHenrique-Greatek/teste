# Manual de Instalação do Git

## Objetivo

O objetivo deste documento é descrever o processo de instalação e configuração do Git para trabalhar com repositórios remotos no GitHub.

## Referências

- [Download Git Bash](https://git-scm.com/downloads)
- [GitHub](https://github.com)

## Processo

### 1. Instalar o Git Bash

O usuário deve ter instalado o Git Bash em sua máquina e uma conta no GitHub.

### 2. Criar um diretório para o repositório

Crie uma pasta onde será clonado o repositório. Em seguida, entre nela, clique com o botão direito e selecione **"Open Git Bash Here"**.

![img1](assets/img1.png)

### 3. Gerar uma chave SSH

Para ter acesso ao repositório, será necessário ter uma chave SSH vinculada ao seu e-mail do GitHub. No Git Bash, execute o seguinte comando, substituindo pelo seu e-mail:

```bash
ssh-keygen -t ed25519 -C "seu-email@example.com"
```

Aperte **Enter** para confirmar o caminho, depois crie uma senha para sua chave SSH (Não perca essa senha).

![img2](assets/img2.png)

Se o comando anterior for bem sucedido, será retornada essa mensagem: 

![img3](assets/img3.png)

### 4. Obter a chave SSH

Execute o seguinte comando para vincular sua chave ao respositório e visualizar a chave SSH gerada:

```bash
cat ~/.ssh/id_ed25519.pub
```

Copie o valor retornado e envie para o administrador do repositório para que seja vinculado ao mesmo.

![img4](assets/img4.png)

### 5. O administrador adiciona a chave ao repositório

O administrador do repositório deve:

1. Acessar **Configurações** no repositório.
2. Navegar até **Deploy Keys**.
3. Clicar em **Add Deploy Key**.

![img5](assets/img5.png)

4. Nomear a chave, colar o valor copiado e marcar a opção correspondente.

![img6](assets/img6.png)

### 6. Clonar o repositório

Após a chave ser vinculada, o usuário pode clonar o repositório. Para isso:

1. No GitHub, vá até o repositório e clique em **Code** > **SSH**.
2. Copie o link SSH fornecido.


3. No Git Bash, execute o comando abaixo (substitua pelo link copiado):

![img7](assets/img7.png)

```bash
git clone git@github.com:dayanaRocha-greatek/Protheus.git
```

![img8](assets/img8.png)

4. Entre no repositório clonado:

![img9](assets/img9.png)

```bash
cd Protheus
```

### 7. Configurar as credenciais do Git

Para poder enviar arquivos ao repositório remoto, é necessário configurar suas credenciais de usuário e e-mail no Git. Execute os comandos:

```bash
git config --global user.name "fulanoTal-greatek"
git config --global user.email "fulanodetal@exemplo.br"
```

### 8. Comandos básicos do Git

Após ter o repositório em sua máquina local, por boas praticas é interessante utilizar o comando:

```bash
    git pull

```

Este comando serve para atualizar o seu repositório local, sempre que houver alguma alteração no repositório em nuvem (GitHub), é obrigatório utilizar para fazer o sincronismo. Caso não faça esse sincronismo pode e irá acontecer conflito entre repositórios quando for enviar os novos arquivos para o repositório em nuvem (GitHub).

```bash
    git commit -m "mensagem do commit"
```

Esse comando serve para fazer um comentário sobre as alterações feitas. A cada alteração que fazer no código, é necessário o uso para manter o versionamento.


```bash
    git push -u origin main
```

O comando git push envia as alterações locais de um repositório para um repositório remoto. Ele sincroniza os commits locais com o repositório remoto, permitindo que outros desenvolvedores acessem essas mudanças..

-u: A opção -u (ou --set-upstream) faz com que o Git associe o branch local com o branch remoto especificado. Isso significa que, após esse primeiro push, você pode usar comandos como git push ou git pull sem precisar especificar o nome do branch e o repositório remoto em comandos subsequentes. Ou seja, ele configura o branch local para rastrear o branch remoto correspondente, tornando mais fácil trabalhar com esse branch no futuro..

origin: origin é o nome padrão dado ao repositório remoto. Geralmente, é o repositório de onde você clonou o projeto ou o repositório principal onde seu código é armazenado. Pode ser configurado com outros nomes, mas origin é o nome mais comum.

main: main é o nome do branch que você está empurrando para o repositório remoto. Tradicionalmente, o branch principal de um repositório Git era chamado de master, mas muitos projetos agora utilizam main como nome padrão para o branch principal..


## Histórico da Documentação

| Versão |   Data   |        Descrição        |       Autor      |
|--------|----------|-------------------------|------------------|
|  1.0   |06/02/2025|Documentação basica em MD|Isaac Souza       |

---




**Endereço:**

Av. Cassiano Ricardo, 319 - Sala 2401  
Jd. Aquarius, São José dos Campos/SP - CEP 12246-870
