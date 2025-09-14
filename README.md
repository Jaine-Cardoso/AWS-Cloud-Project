# Meu Projeto Cloud
Fundada por Jeff Bezzos em 2006. Pioneira na infraestrutura cloud.

Atualmente AWS tem disponibilidade de serviços em 105 zonas em 33 regiões.

**Regions e Avaibility Zones**

Regions:São áreas geográficas contendo várias Avaibiliaty Zones.
Regions:São projetadas para ser isoladas das outras regiões. Isso proporciona a maior tolerância a falhas e estabilidade possível. Uma região é composta por 2 ou mais zonas de disponibilidade.

Alguns pontos que devemos levar em consideração, quando for escolher uma região.

- Complaice( conformidade)
- Disponibilidade de Serviços
- Custo
- Latência

Avaibiliaty Zones: são datas centers independentes fisicamente, mas conectados logicamente, para garantir alta disponibilidade.geralmente existem 2 por região.


Zonas de Disponibilidade:Cada região é independente das demais regiões, o que significa que os recursos são exclusivos da região escolhida em que está sendo provisionado os recursos.
Isso contribui para maior tolerância a falhas e não há replicação automática entre as regiões, isto deve ser habilitado pelo administrador da conta.
[ ! a imagem mostra as regions e as avaibiliaty zones]

**Modelo de negócio AWS**

Modelo cloud OPEX quando não necessita de grande infraestrutura para iniciar um projeto.

Diferente do modelo CAPEX que precisamos de uma infraestrutura física para começar o projeto.
 
**Modelos de Computação na Nuvem**

- IaaS- ( infraestrutura as a Service) é tudo aquilo que eu vou migrar, tudo aquilo que eu construí do zero.

- PaaS- ( Plataforma as a Service) é tudo aquilo que eu vou pegar minha solução e implantar.Web, desenvolvimento de alguma aplicação.

- SaaS- ( Software as a Service) é tudo que você paga pra ultilizar>Ex: E-mail, Gmail, Spotify, Netflix.Resumindo é aquele serviço que está pronto,o usúario faz login e acessa.

[! a imagem mostra os modelos de computação em nuvem]

**Configurações da conta AWS**

Priorizando sempre a segurança,é importante saber que a criação de toda conta cloud você terá uma conta principal (root) com super permissões ao seu workspace. Por isso é importante criar outros usuários com IAM.O que é o IAM. Mas o que são esses usuários?

**O IAM é Identity and Access Management**

Gerenciamento de acesso, gerenciamento de identidade.
São perfis que você determina os acessos dentro da plataforma.
Esses usuários podem ser criados a partir da conta root. 
Procure IAM, vá ao Painel e clique em usuários, crie um novo usuário e dê permissões de acordo com cada função que será exercida por esse usário.
Também é possível criar grupos para esses usuários. assim fica mais fácil o acesso da equipe de gerenciamento e administração.

[! a imagem mostra o painel de usuários em uma conta na AWS]

**Autenticação multifator (MFA)**
A Autencicação multifactor ajuda a manter a conta sempre protegida, gerando códigos aleatórios ao fazer o login.

**Formas de criar os meus recursos na AWS**

- Via portal
- Via AWS SDK
- Cloud Shell

**O que são as instâncias EC2?**
EC2 - Elastic Compute Cloud, são as máquinas virtuais na AWS, podendo ser com sistema operacional Windows ou Linux.
Os tipos de instância oferece diferentes recursos de computação como memória e armazenamento e é agrupado em famílias de instâncias com base nesses recursos.

Uma EC2 é composta por uma 

- CPU
- Memória
- Rede
- Disco
- Sistema operacional


No modelo Cloud, uma EC2 é do tipo IaaS ou seja, quando criamos a EC2 estamos utilizando o tipo de infraestrutura como serviço.

E qual seria nossa responsabilidade sobre este recurso?
Seria dos aplicativos, dados e conexões que fazemos.


**Como escolher a EC2 de forma correta para a minha aplicação?**

 Escolher a instância correta na AWS é crucial para garantir eficiência,escalabilidade e economia nos gastos com nuvem.
Escolher a instância certa não se trata apenas de selecionar um tipo aleatório, mas sim de entender as necessidades de sua aplicação e utilizar os recursos da nuvem de forma inteligente para alcançar eficiência operacional e econômica.

[ ! a imagem mostra como criar uma estimativa de custo na AWS princing calculator]
[! a imagem mostra o valor dos custos ao criar uma EC2]
 
**EC2 - Terminologia**

O Amazon Elastic Computer Cloud(EC2) nos fornece a capacidade de computação na cloud AWS.
As imagens de máquina da Amazom estão disponíveis para a escolha no momento da criação
Pode definir a segurança básica utilizando firewall incorporada do AWS, utilizando grupo de segurança, protocolo, porta, IPs de origem que permitem negar acesso às suas instâncias EC2.



**Otimização de Recursos**

Quando falamos em otimização de recursos, estamos apontando para "custo", ou seja, otimizar recursos é poupar custos na AWS.

Mesmo otimizando recurso computacional, onde melhoramos o desempenho do sistema, estamos poupando custo, pois isto traz ganho para a nossa solução na nuvem.

[! a imagem mostra um exemplo de otimização de recursos]

**Desligando instâncias não utilizadas**

Em ambientes produtivos não há a necessidade, mas em ambientes como desenvolvimento, testes, treinamento, geralmente não são utilizados nos períodos noturnos ou finais de semana e podem ser desligados.
Uma menor utilização implica diretamente em economia de custos,è importante remover recursos ociosos ou não utilizados.
É comum criarmos recursos e não verificar a utilização e ficarmos com vários recursos ociosos no ambiente isto gera gastos.
Não é só fazer o stop tem que fazer o realocation se não continua pagando os custos como se tivessem usando normalmente.



**Escalar recursos**

Nós executamos o scale de recursos para processar os worldoads em determinados momentos.

Temos a opção de aumentar ou diminuir de forma manual ou automática.

Escalar horizontalmente= é quando aumenta o número de recursos. Por exemplo, adicionando mais um disco rígido, adicionando mais uma instância para suportar a aplicação.

Escalar verticalmente = acrescentar ou reduzir a capacidade de um recurso em um mesmo nó e geralmente está relacionado a alterar o número de vCPUs , memória, storage, rede de uma instância.

**Sob demanda (on-demand)**

As instâncias on- demand são compradas a uma taxa fixa por hora e são recomendadas para aplicativos com cargas de trabalho irregulares de curto prazo que não podem ser interrompidaz. Elas também são adequados para o uso durante o teste e desenvolvimento de aplicativos no EC2.


**Instâncias reservadas**

Costumam ser mais baratas que as instâncias on-demand, mas você precisa pagar o ano inteiro de uso. É uma desvantagem para quem não precisa usar a instância com frequência.


**Instância SPOT**

Garante a disponibilidade das aplicações sob demanda com descontos de 90%. A desvantagem das instâncias SPOT é que elas podem ser encerradas pela AWS a qualquer momento, com aviso de dois minutos.



**Armazenamento na Nuvem com Amazon EBS e S3**


Amazon EBS - Elastic Block Store(EBS) , nada mais é do que uma storage altamente confiável que pode ser anexado em qualquer instância EC2. Toda instância possui um volume de armazenamento.

Agora com o EBS conseguimos ter a capacidade de expansão de forma rápida, com apenas alguns clicks.

(Ele é tipo um HD externo)

Então com o EBS conseguimos criar uma nova partição em nossa instância, seria como anexar um HD externo. Escolhemos o modelo e o site e anexamos a nossa VM.

Exemplo de uso:

Armazenamento para banco de dados, como My SQL, PostgreSQL e Oracle.
Armazenar dados para aplicativos web e logs de sistema.


**S3**

Amazon S3 ( Amazon Simple Storage Service) é um serviço de armazenamento de objetos sem nuvem oferecidos pela AWS.

É ideal para armazenar, organizar e recuperar grandes volumes de dados de forma segura e escalável.
O Amazon S3 possui algumas classes de storages onde conseguimos economizar nos custos.
Um exemplo muito bom para entrarmos as diferentes classes do S3 é o exame de Hospital
99.999999999% de disponibilidade.
Podemos utilizar regra de ciclo de vida a forma como o Amazin S3 gere os objetos durante o seu tempo de vida.
Lifecycle permite fazer a transição de objetos e migrar automaticamente para a classe Glacier.


**Imagem de máquina da Amazon(AMI)**

No Amazon EC2 (Elastic Compute Cloud), uma AMI (Amazon Machibr Image) é uma imagem de máquina virtual pré configurada, que inclui as informações necessárias para iniciar uma instância, como o sistema operativo, o servidor de aplicações e as aplicações.
[ ! a imagem mostra um desenho de arquitetura]
[! a imagem mostra um modelo de arquiteura]

**Snapshot com EBS**

Quando falamos sobre infraestrutura, isto tem a ver com o disco servidor virtual, vale lembrar que quando falamos de infraestrutura estamos falando de modelo cloud.
Neste caso, estamos falando sobre o modelo IaaS.
O Snapshit do EBS é um serviço de backup nativo do AWS que faz backups dos volumes do EBS em um determinado momento.
E é possível configurar a frequência com que os snapshots são tirados.
Criação  e uso de imagens AMI.jpeg

Conclusão:
Os Snapshots do Amazon EBS são cópias em pontos no tempo de um volume do Amazon EBS, armazenadas no Amzon S3.Eles podem ser usados para criar volume do Amazon EBS, aumentar a durabilidade de dados e fornecer um mecanismo de backup e restauração para volumes do EBS.








