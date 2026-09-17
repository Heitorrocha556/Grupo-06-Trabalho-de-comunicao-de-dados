# Projeto Prático 8 — Rede Corporativa com Rapid PVST+ e DAI

## Informações acadêmicas

- Centro Universitário do Planalto Central Apparecido dos Santos - UNICEPLAC
- Curso: Engenharia de Software
- Professor: Hudson Neves e Silva
- Local: Gama - DF
- Ano: 2026

### Integrantes

- Alexsander Sávio Santana da Silva
- Gabriel Santos Araújo
- Geovana Rosal Torres
- Gustavo Viana Pereira
- Heitor Rocha Moreira
- Kaio Rauan da Silva Matias
- Lara Isabela Lima Serra
- Letícia Liz Benigno da Silva
- Pedro Henrique Eduardo Ribeiro Costa

### Projeto

Sistema Gerenciador de Orçamento Pessoal

## Sobre o projeto

Este projeto foi desenvolvido no Cisco Packet Tracer como parte da disciplina de Redes de Computadores, com foco na criação de uma infraestrutura local corporativa resiliente, redundante e segura.

A simulação foi estruturada em conformidade com o enunciado do projeto, incluindo múltiplas VLANs, switches multicamada, switches de acesso, servidores locais e computadores finais, além da configuração de segurança de rede para proteção da infraestrutura.

O arquivo do projeto está disponível em [`Trabalho 01.pkt`](./Trabalho%2001.pkt). Esse arquivo deve ser aberto no Cisco Packet Tracer para visualizar e interagir com a topologia, os dispositivos e as configurações aplicadas.

## Objetivos

- Construir uma rede corporativa local com 35 a 45 dispositivos;
- Garantir redundância de enlaces e caminho alternativo sem loop;
- Configurar Rapid PVST+ para convergência rápida de camada 2;
- Segmentar a rede em VLANs dedicadas por setor;
- Implementar DHCP Snooping e Dynamic ARP Inspection (DAI);
- Aplicar Port Security para proteção contra portas com MAC não autorizada;
- Validar a continuidade da rede e a segurança da infraestrutura.

## Topologia obrigatória

A infraestrutura foi organizada seguindo o escopo definido no projeto:

- 2 switches multicamada (Core switches Layer 3 em alta disponibilidade);
- 3 switches de acesso Layer 2 (Engenharia, Qualidade e Suporte);
- 2 servidores locais;
- 25 a 30 dispositivos finais distribuídos entre os setores.

## Estrutura da rede

### 1. Core switches

Os switches centrais configurados como Core 1 e Core 2 foram responsáveis por:

- interconexão entre os acessos e os servidores;
- roteamento inter-VLAN;
- manutenção da redundância de camada 2;
- definição da raiz principal e secundária do STP;
- suporte à convergência rápida com Rapid PVST+.

### 2. Switches de acesso

Os switches de acesso foram distribuídos conforme os setores da empresa:

- Engenharia;
- Qualidade;
- Suporte.

Cada um deles expôs as estações finais do setor e conectou-se aos cores por uplinks redundantes.

### 3. Servidores locais

Os servidores implementados atendem às funções de:

- Repositório interno;
- Autenticação e DNS.

Esses dispositivos foram posicionados em VLAN específica para manter a segmentação e a segurança da rede.

### 4. Estações finais

A rede foi composta por computadores de mesa cabeados, distribuídos pelos setores da organização e conectados aos switches de acesso conforme a VLAN correspondente.

## Segmentação e endereçamento

A rede corporativa foi segmentada em VLANs dedicadas para separar os diferentes tipos de tráfego e manter a organização lógica da infraestrutura.

### VLANs sugeridas

- VLAN 10 — Engenharia
- VLAN 20 — Qualidade
- VLAN 30 — Suporte
- VLAN 40 — Servidores
- VLAN 99 — Gerenciamento

Essa segmentação permite isolar o tráfego dos setores e controlar melhor o acesso aos recursos internos da empresa.

## Requisitos técnicos implementados

### Rapid PVST+

O protocolo Rapid Spanning Tree foi configurado para garantir:

- eliminação de loops em rede redundante;
- convergência rápida após falha de link;
- escolha dos caminhos ideais em camada 2;
- maior estabilidade da infraestrutura local.

### Dynamic ARP Inspection (DAI)

A proteção contra spoofing ARP foi implementada utilizando:

- DHCP Snooping;
- validação de mensagens ARP;
- bloqueio de pacotes ARP falsificados nas portas de acesso;
- mitigação de ataques de envenenamento de cache ARP.

### Port Security

A política de segurança por porta foi configurada para:

- limitar o número de endereços MAC por interface;
- bloquear automaticamente a porta em caso de violação;
- gerar estado de erro `err-disabled` quando um dispositivo não autorizado tenta se conectar.

## Arquitetura lógica

A infraestrutura foi projetada para operar com redundância estrutural sem loops, com o seguinte comportamento:

- cada access switch conecta-se aos dois core switches;
- os core switches se interligam entre si para redundância;
- os usuários são conectados em VLANs setoriais;
- os servidores permanecem em segmento isolado;
- a decisão de caminho é feita por Rapid PVST+;
- a segurança de camada 2 é reforçada por DAI e Port Security.

## Validação do projeto

A entrega do desafio exige comprovar, por meio do Packet Tracer, que a infraestrutura funciona corretamente.

### Teste de convergência de link

- simular falha de um cabo principal entre switches;
- verificar a reconvergência da rede pela mudança de caminho;
- confirmar que a conectividade continua disponível;
- avaliar o tempo de restabelecimento do serviço.

### Validação de inspeção ARP

- disparar um ARP Reply falso de um dispositivo não autorizado;
- verificar que o switch bloqueia a mensagem;
- confirmar que o pacote é descartado antes de afetar a tabela ARP.

### Verificação de Port Security

- conectar um equipamento extra em uma porta com limite de MAC atingido;
- verificar que a interface entra em `err-disabled`;
- confirmar que a violação é detectada e bloqueada pela política.

## Configurações principais

A estrutura lógica da rede foi configurada com base em:

- ativação de `ip routing` nos switches multicamada;
- criação das VLANs;
- configuração de SVI para roteamento inter-VLAN;
- ativação de `spanning-tree mode rapid-pvst`;
- definição de raiz primária e secundária no STP;
- configuração de trunks e ports de acesso;
- habilitação de DHCP Snooping;
- ativação de DAI em VLANs corporativas;
- configuração de Port Security com violação em shutdown.

## Arquivos do repositório

| Arquivo | Descrição |
| --- | --- |
| [`Trabalho 01.pkt`](./Trabalho%2001.pkt) | Arquivo da simulação no Cisco Packet Tracer com a topologia e as configurações da rede. |
| [`README.md`](./README.md) | Documentação do projeto e descrição da infraestrutura. |

## Como abrir o projeto

1. Instale o Cisco Packet Tracer.
2. Abra o arquivo [`Trabalho 01.pkt`](./Trabalho%2001.pkt).
3. Verifique a topologia da rede e os dispositivos envolvidos.
4. Acesse as configurações dos switches para consultar VLANs, interfaces e protocolos.
5. Realize testes de ping e validação de conectividade.
6. Simule falhas de enlace e observe o comportamento do Rapid PVST+.
7. Teste a segurança ARP e o comportamento de Port Security.

## Observações

- O arquivo `.pkt` é um arquivo binário proprietário do Cisco Packet Tracer, portanto não é possível visualizar a topologia completa apenas como texto.
- Para uma análise detalhada, a melhor forma é abrir o arquivo no próprio software e inspecionar os dispositivos, interfaces e configurações.
- O projeto foi pensado para atender às exigências do enunciado, com foco em escalabilidade, redundância e segurança da rede local.

## Conclusão

O Projeto Prático 8 foi implementado para demonstrar os conceitos de redes corporativas modernas, enfatizando redundância, convergência rápida e proteção contra ataques de camada 2. A combinação de Rapid PVST+, DHCP Snooping, DAI e Port Security foi aplicada para garantir uma infraestrutura segura, estável e funcional em um ambiente corporativo simulado.

---

Desenvolvido para a disciplina de Redes de Computadores, com simulação realizada no Cisco Packet Tracer.
