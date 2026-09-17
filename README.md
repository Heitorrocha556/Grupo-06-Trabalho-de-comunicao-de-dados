<p align="center">
  <img src="https://media.giphy.com/media/l41YvpiA9uMWw5AMU/giphy.gif" alt="Simulação de redes" width="220" />
</p>

<h1 align="center">Trabalho 01 — Simulação de conexão de redes</h1>

<p align="center">
  Projeto desenvolvido no <strong>Cisco Packet Tracer</strong> para a disciplina SSC0540 — Redes de Computadores, ICMC — USP.
</p>

## Sobre o projeto

O **Trabalho 01** consiste em uma simulação de rede criada no Cisco Packet Tracer. O objetivo é representar a infraestrutura de duas unidades e permitir a comunicação entre elas, considerando a configuração física, a configuração lógica e o custo dos componentes utilizados.

O projeto está armazenado no arquivo [`Trabalho 01.pkt`](./Trabalho%2001.pkt). Esse arquivo deve ser aberto no Cisco Packet Tracer para visualizar a topologia, os dispositivos, os enlaces e as configurações realizadas.

## Objetivos

A simulação foi organizada para atender aos seguintes objetivos:

- Criar a infraestrutura de rede das unidades propostas;
- Representar a planta de cada unidade como plano de fundo do projeto;
- Definir a disposição física dos equipamentos;
- Configurar logicamente os dispositivos da rede;
- Estabelecer a comunicação entre as duas unidades;
- Utilizar componentes adequados, buscando o melhor custo-benefício;
- Validar a conectividade entre os dispositivos por meio das ferramentas do Packet Tracer.

## Análise do Trabalho 01

### 1. Infraestrutura física

A primeira etapa do trabalho é a representação física das unidades no Packet Tracer. Nessa etapa devem ser considerados:

- Os dispositivos finais utilizados em cada unidade;
- Os equipamentos responsáveis pela interligação da rede;
- A organização dos componentes de acordo com a planta;
- Os cabos e enlaces necessários para conectar os dispositivos;
- A identificação dos equipamentos e das respectivas unidades.

A visualização física pode ser conferida diretamente no arquivo `.pkt`, pois o formato original preserva a posição dos dispositivos e a organização da topologia.

### 2. Configuração lógica

A configuração lógica é responsável por permitir que os dispositivos se comuniquem. Ela envolve, de acordo com a topologia criada no Packet Tracer:

- Endereçamento IP dos dispositivos;
- Máscaras de sub-rede;
- Configuração das interfaces dos equipamentos de rede;
- Definição de gateways;
- Organização dos dispositivos por unidade ou segmento de rede;
- Testes de comunicação entre os pontos da simulação.

Como o arquivo `.pkt` é binário e não pode ser convertido diretamente para Markdown, os endereços e demais parâmetros devem ser consultados dentro do Cisco Packet Tracer, nas configurações dos dispositivos.

### 3. Comunicação entre as unidades

O requisito central do Trabalho 01 é permitir a comunicação entre as duas unidades. Para validar essa comunicação, é possível utilizar:

- `ping` entre computadores de unidades diferentes;
- Testes de conectividade nas interfaces dos roteadores e switches;
- Verificação do estado dos enlaces;
- Simulação do envio de pacotes pela ferramenta **Simulation** do Packet Tracer.

Uma comunicação bem-sucedida indica que o cabeamento, o endereçamento e as configurações dos dispositivos foram definidos de forma compatível.

### 4. Custo-benefício

A infraestrutura deve atender aos requisitos do projeto sem adicionar equipamentos desnecessários. A escolha dos componentes deve levar em conta:

- Quantidade de dispositivos necessários;
- Função de cada equipamento;
- Capacidade de expansão da rede;
- Facilidade de configuração e manutenção;
- Redução de pontos de falha e de custos de implantação.

## Arquivo do projeto

| Arquivo | Descrição |
| --- | --- |
| [`Trabalho 01.pkt`](./Trabalho%2001.pkt) | Arquivo binário com a topologia, os dispositivos e as configurações da simulação. |

## Como abrir e executar

1. Instale o [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer).
2. Baixe o arquivo [`Trabalho 01.pkt`](./Trabalho%2001.pkt).
3. Abra o arquivo no Cisco Packet Tracer utilizando **File > Open**.
4. Analise a disposição física dos dispositivos e os enlaces entre as unidades.
5. Acesse as configurações dos equipamentos para consultar ou ajustar os endereços IP.
6. Execute testes de conectividade, como `ping`, entre dispositivos das duas unidades.
7. Utilize o modo **Simulation** para acompanhar o caminho dos pacotes pela rede.

> Recomenda-se utilizar uma versão do Cisco Packet Tracer compatível com a versão em que o projeto foi criado. Caso algum dispositivo não seja exibido corretamente, abra o arquivo em uma versão próxima à utilizada no desenvolvimento.

## Download

[Baixar Trabalho 01.pkt](https://github.com/Heitorrocha556/Readme.Md/raw/main/Trabalho%2001.pkt)

## Repositório

- [Arquivo do projeto no GitHub](https://github.com/Heitorrocha556/Readme.Md/blob/main/Trabalho%2001.pkt)

## Observação

O arquivo `.pkt` é um formato proprietário e binário do Cisco Packet Tracer. Por esse motivo, não é possível documentar sua topologia completa apenas lendo o conteúdo do arquivo como texto. A análise detalhada dos dispositivos, endereços, cabos e configurações deve ser feita com o projeto aberto no Packet Tracer.
