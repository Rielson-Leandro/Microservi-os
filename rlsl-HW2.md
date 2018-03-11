# <center>Homework 2</center>

#### Rielson Leandro - rlsl
#### Ciência da Computação

<br>

     2.1. What are the relationships with other architecture styles ?

## O que é SOA ?

Uma arquitertua orientada à serviços segundo a Wikipedia: "Funcionalidades impementadas pelas aplicações devem ser disponibilizadas através de serviços". Esse serviços podem ser consumidos por outros serviços para que o todo forme um sistema complexo. É o classico "dividir para conquistar".

## O que é microservices?

Microservices focam em endpoints inteligentes (os serviços) e canais de comunicação burros (Protocolos simples, como REST). Aplicações construidas a partir de microservices possuem o objetivo (e a regra) de serem tão desacopladas e coesas quanto for possível.
O grande desafio dos times que querem trocar de padrão de arquitetura: monolítica para microservices é que p "normal" na indústria é que os componentes se comuniquem através de inovação de métodos ou chamada de funções e é mudar esse padrão de comunicação que mora o grande desafio.

## Microservices Vs SOA

1. ##### Como funciona a arquitetura monolítica

As principais principais linguagens de desenvolvimento oferecem abstrações ara quebrar a complexidade dos sistemas em módulos. Entretanto, são projetadas para a criação de uma único executável monolítico, onde toda a modularização utilizada é executada em uma mesma máquina. Os módulos compartilham recursos de processamento, memória, bancos de dados e arquivos. 

Uma arquitertura de monolítica típica de um sistema complexo pode ser representada pela figura abaixo, onde todas as funções do negócio estão implementadas em um único processo. 



 ![SOA](https://i2.wp.com/blog.caelum.com.br/wp-content/uploads/2015/01/monolitico.png?w=300)

 Ao longo do tempo o sistema vai crescendo e tornando-se cada vez mais complexo, consumindo cada vez mais recursos. Surgem tambpem alguns desafios para manutenção: 

+ ###### Aumento da complexidade e tamano ao longo do tempo:
    * O Sistema  torna-se muito complexo e a manutenção fica cada vez mais enta e cara

+ ###### Alta dependência de componentes de código
    * Muitas funções são interdependentes e entrelaçadas, de forma que a inclusão ou manutenção de componentes podem causas inconsistências

+ ###### Escalabilidade do sistema é limitada
    * Exige que todo o sistema seja replicado mesmo que apenas parte de sua funcionalidade.

+ ###### Falta de flexibilidade
    * Exige que os desenvolvedores fiquem amarrados à tecnologia originalmente escolhida

+ ###### Dificuldade para colocar alterações em produção
    * Qualquer mudança, por menor que seja, requer a reinicialização do sistema. 

2. ##### Como funciona a arquitetura de micro serviços
A arquitetura de **micro serviços** é utilizada para desenvolver uma aplicação como um conjunto de pequenos serviços, cada um funcionando em seu próprio processo. Cada serviço é desenvolvido em torno de um conjunto de regras de negócio especifico, e é implementado de forma independente.

 ![Microservices](https://i2.wp.com/blog.caelum.com.br/wp-content/uploads/2015/01/microservicos.png?w=500)

Com isso, podemos quebrar algumas barreiras existentes no modelo de arquitetura monolítica: 

+ ###### Mannutenção e evolução dos serviços mais estáveis 
    * Os desenvolvedores tratarão de códigos que execultam uma única função, e cada serviço individual não cresce indefinidamente com o crescimento do sistema.

+ ###### Serviços com baixo nível de acoplamento e interdependência
    * Dessa forma, a manutenção em um serviço não interfere diretamente em outras funcionalidades

+ ###### Escalabilidade do sistema
    * É obtida com o deploy e replicação de micro serviços através da infraestrutura de servidores, máquinas virtuais e containers de forma independente.

+ ###### Redução de custos
    * Como cada aplicação só utiliza os serviços de que necessita, os custos são diretamente associados à funcionalidade e à carga de uso do sistema.

+ ###### Flexibilidade de tecnologia
    * Não é necessário amarrar os desenvolvedores a uma tecnologia específica, pois há baixo acoplamento entre os serviços. Dessa forma, pode ser utilizada a melhor tecnologia para atender a cada caso.

+ ###### Facilidade de colocar alterações em produção
    * As mudanças no sistema são feitas através das alterações e evoluções feitas nos serviços. Assim, não existe um sistema que precisa ser reinicializado para continuar funcionando.

3. ##### Governança descentralizada
Tanto em microservices quanto em SOA temos algum nível de governaça dos serviços. No entanto, em SOA, ela é mais centralizada. 

Uma das consequências de governança centralizada é a tendência a se criar padrões em torno de uma única plataforma de tecnologia. Grandes empresas acreditam que devemos sempre utilizar a ferramenta certa para cada trabalho, mas os grandes problemas são:

+ Que aas aplicações monolíticas não nos dão toda a liberdade que queremos para fazer isso;
+ E que o SOA tem padrões demais para serem seguidos, o que acaba engessando os serviços;

Ao quebrar os componentes de uma aplicação monolítica em serviços nós permitimos que cada um deles seja implementados em tecnologias diferentes e use a persistências diferentes e talvez essa seja o maior atrativo de microservices.

4. #### Gerenciamento descentralizado de dados
Novamente, é muito comum vermos implementações de SOa onde temos uma única base de dados centralizadora de tudo.
Uma grande premissa é a de que todos os dados são da mesma empresa, lofo são os mesmos em todos serviços. No entanto, isso nao é 100% verdade.

A descentralização do gerenciamento de dados apresent-se de diferentes maneiras e, em um nível mais abstrato, significa que o modelo conceitual de mundo é diferente entre os sistemas, logo não há porque juntá-lo em uma banco.

Este problema e comum entre aplicações diferentes mas pode ocorrer mesmo dentro de uma única aplicação, principalmente quando ela é dividida em componentes separados. 

Assim como pensar sobre os modelos conceituais de dados nos leva a pensar que eles deveriam ser separados, usar microservices reforça, e muito, esse mindset. enquanto aplicações monolíticas preferem bases únicas e centralizadoras por padrão, microservices preferem deixar que cada serviço escolha a melhor maneira de persistir os seus dados, seja com a mesma base de dados, a mesma tecnologia mas bases diferentes ou tecnologias competamente diferentes.
 ![Minion](https://martinfowler.com/articles/microservices/images/decentralised-data.png)

> ###### referência: 
>  [Martin Fowler](https://martinfowler.com/)