# MySQL em Docker com persistência.

<p align="center">
<img src="https://img.shields.io/badge/ STATUS-LANÇADO (desenvolvido)-brightgreen"/>
</p>
<p align="center">
<img src="https://img.shields.io/badge/ STATUS-VERSÃO 1.0-brightgreen"/>
</p>

## Descrição

<p align="justify">

Este projeto foi criado para resolver a dificuldade de instalar o `MySQL` a cada troca de máquina, seja no `Linux` ou no `Windows`. Frequentemente, instalar e configurar o `servidor` MySQL era um processo tedioso e demorado. Para `simplificar` essa tarefa, estou compartilhando uma maneira `prática e eficiente` de utilizar o MySQL através de contêineres [Docker](https://www.docker.com/). 

Desenvolvido por [Wesley Pereira](https://github.com/wesleyp846).

</p>

## Motivação

<p align="justify">

A ideia surgiu da necessidade de ter uma solução consistente e `fácil de implementar`, independentemente do sistema operacional em uso. Com o  [Docker](https://www.docker.com/), você pode criar um ambiente MySQL de forma `rápida` e homogênea, sem se preocupar com as peculiaridades de cada sistema.

</p>

## Benefícios

- **Facilidade de uso**: Configuração simples e rápida do MySQL em `qualquer sistema operacional`.
- **Persistência de dados**: Seus dados são armazenados em uma `pasta à sua escolha`, mesmo quando o contêiner `não está rodando`.
- **Portabilidade**: O mesmo procedimento funciona tanto no Linux quanto no Windows.

### Pré-requisitos

- Docker instalado
- Acesso à internet

### Implementação

1. **Download da imagem do MySQL**
    
    Para começar, faça o download da imagem `oficial` do MySQL do `Docker Hub` usando o seguinte comando:
    
    ```bash
    docker pull mysql:latest
    ```
    > Demonstração no terminal

![Demonstração no terminal do camando para baixar a imagem](https://github.com/wesleyp846/Conteiner_mysql_docker/blob/main/primeiroComando.png)

2. **Rodar o contêiner com variáveis de ambiente**
    
    Em seguida, execute o `contêiner` configurando as `variáveis de ambiente` para definir o usuário, senha, pasta de persistência, entre outras. Use o comando abaixo, ajustando os valores conforme necessário:
    
    ```bash
    docker run --name my-mysql-container -e MYSQL_ROOT_PASSWORD=suasenha -e MYSQL_DATABASE=seubanco -e MYSQL_USER=seuusuario -e MYSQL_PASSWORD=suasenhausuario -v /path/para/sua/pasta:/var/lib/mysql -d mysql:latest
    ```
    
    Onde `/path/para/sua/pasta:/` será a pasta onde ficará `persistido` o seu banco de dados.
    
3. **Exemplo**
    
    Para exemplo criamos um contêiner de nome `my-mysql-container` , senha do administrador  `root`, pasta de persistência em  `/home/wesley/Área de Trabalho/alura_mysql` e utilizando a imagem `mysql:latest`
    
    ```html
    docker run --name my-mysql-container -e MYSQL_ROOT_PASSWORD=root -v "/home/wesley/Área de Trabalho/alura_mysql":/var/lib/mysql mysql:latest
    ```
   
    > Demonstração no terminal

![Demonstração no terminal do camando para montar o contêiner](https://github.com/wesleyp846/Conteiner_mysql_docker/blob/main/segundoComando.png)
  
    Em um `segundo terminal ou aba`, para listar os contêiner’s rodando e revelar seu `id’s`
    
    
    docker ps
    
O contêiner de nome escolhido na variável  `--name my-mysql-container`, aparecerá aqui.
    
> Demonstração no terminal

![Demonstração no terminal do camando para listar o contêiner](https://github.com/wesleyp846/Conteiner_mysql_docker/blob/main/terceiroComando.png)

caso contrário o contêiner pode ter sido `interrompido`. substitua o ultimo comando por 
    
    
    docker ps -a  
    
    
Com o `id` do contêiner, execute
    
    
    docker exec -it 5121702520bc bash
    
    
Onde `-it` é opção para o modo interativo e `bash` para acessar o terminal do contêiner

Por fim 
    
    mysql -uroot -p
       
Onde -u`root` é o usuário root, `-p` para digitar a senha.
    
> Demonstração no terminal

![Demonstração no terminal da execução do contêiner](https://github.com/wesleyp846/Conteiner_mysql_docker/blob/main/ultimaTela.png)

<br>

## Versão Atual: 1

Na versão 1, a aplicação foi `finalizada`, `Dockerizada` e `entregue`.

<br>

> Pré-requisitos
> 
- Acesso à `WEB`.
- `Doker`

<br>

> Tecnologias Utilizadas
> 

[Docker](https://www.docker.com/): Usado na conteinerização da aplicação como um todo.

<br>

> Funcionalidades
> 
1. A aplicação permite a `criação e gerenciamento de bancos de dados`.
2. `Compatível` com todos os SO com o Docker instalado.

<br>

### Contribuição

> Licença
MIT
> 

<br>

> Créditos
> 

Esperamos que esta documentação ajude você a compreender a aplicação.

Fique à vontade para contribuir e adicionar melhorias ao código.

Para mais informações, visite o `LinkedIn` de [Wesley Pereira](https://www.linkedin.com/in/wesleyp846).

Visite também o`GitHub`de [Wesley Pereira](https://www.linkedin.com/in/wesleyp846).

Primeiro commit na data de 16/08/2024
