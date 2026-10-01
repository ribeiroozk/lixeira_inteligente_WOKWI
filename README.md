# 🗑️ Lixeira Inteligente — Projeto IoT Conectado à Nuvem

## 📖 Sobre o Projeto

Este projeto consiste no desenvolvimento de uma **Lixeira Inteligente utilizando Internet das Coisas (IoT)**, com o objetivo de monitorar o nível de preenchimento de uma lixeira e facilitar o gerenciamento da coleta de resíduos em cidades inteligentes (*Smart Cities*).

A solução utiliza uma placa ESP32 e um sensor ultrassônico HC-SR04 para identificar a distância entre o sensor e o lixo acumulado. A partir dessa informação, é possível estimar a porcentagem de ocupação da lixeira, indicar seu nível de preenchimento por meio de LEDs e enviar os dados para um painel de monitoramento na nuvem.

O protótipo é desenvolvido e testado no simulador Wokwi, com integração a uma plataforma de IoT em nuvem, como ThingSpeak ou Adafruit IO.

## 🎯 Objetivo

Desenvolver e simular uma solução IoT capaz de monitorar o nível de preenchimento de uma lixeira, contribuindo para otimizar as rotas de coleta de resíduos, melhorar a organização da limpeza urbana e reduzir deslocamentos desnecessários dos veículos de coleta.

## 🚨 Problema Identificado

A coleta de lixo pode ser prejudicada pela falta de informações atualizadas sobre o nível de preenchimento das lixeiras. Isso pode resultar em recipientes transbordando ou em coletas realizadas quando ainda não são necessárias.

A Lixeira Inteligente busca solucionar esse problema por meio do monitoramento contínuo e do envio de informações atualizadas sobre a ocupação do recipiente.

## 💡 Solução Proposta

O sistema utiliza um sensor ultrassônico para medir a distância entre o sensor e a superfície do lixo. O ESP32 processa essa medição e calcula uma estimativa da porcentagem de preenchimento da lixeira.

LEDs indicadores podem representar diferentes níveis de ocupação:

* 🟢 **Verde:** lixeira com baixo nível de preenchimento.
* 🟡 **Amarelo:** lixeira com nível intermediário de preenchimento.
* 🔴 **Vermelho:** lixeira próxima da capacidade máxima ou cheia.

Os dados podem ser enviados pela conexão Wi-Fi para um painel na nuvem, permitindo acompanhar as medições durante a simulação.

## ⚙️ Funcionamento do Sistema

O funcionamento da solução segue estas etapas:

1. O sensor ultrassônico HC-SR04 mede a distância até o lixo.
2. O ESP32 recebe e processa os dados coletados.
3. O sistema calcula a porcentagem estimada de preenchimento da lixeira.
4. Os LEDs são acionados conforme o nível identificado.
5. O ESP32 utiliza a conexão Wi-Fi para enviar os dados à plataforma de nuvem.
6. O painel apresenta as informações recebidas para facilitar o monitoramento.

## 🔗 Arquitetura do Projeto

**Sensor Ultrassônico HC-SR04 → ESP32 → Wi-Fi → Plataforma na Nuvem → Dashboard**

## 🔌 Componentes Utilizados

| Componente                  |          Quantidade | Função                                           |
| --------------------------- | ------------------: | ------------------------------------------------ |
| ESP32                       |                   1 | Processar os dados e estabelecer a conexão Wi-Fi |
| Sensor ultrassônico HC-SR04 |                   1 | Medir a distância até o lixo                     |
| LED verde                   |                   1 | Indicar baixo nível de preenchimento             |
| LED amarelo                 |                   1 | Indicar nível intermediário                      |
| LED vermelho                |                   1 | Indicar nível elevado de preenchimento           |
| Resistores                  | Conforme o circuito | Limitar a corrente dos LEDs                      |
| Protoboard e jumpers        | Conforme o circuito | Realizar as conexões elétricas                   |

**Observação:** os componentes são utilizados na montagem simulada no Wokwi. Para uma implementação física, também devem ser considerados alimentação elétrica, proteção dos circuitos e condições ambientais.

## 🛠️ Tecnologias e Ferramentas

* **ESP32:** microcontrolador com conectividade Wi-Fi.
* **C/C++:** linguagem utilizada para programar o sistema.
* **Arduino:** ambiente e bibliotecas de programação do ESP32.
* **Wokwi:** simulador para montagem e execução do circuito eletrônico.
* **ThingSpeak ou Adafruit IO:** plataformas possíveis para receber, armazenar e visualizar os dados na nuvem.
* **Wi-Fi:** comunicação entre o protótipo e a plataforma de monitoramento.
* **GitHub:** hospedagem e documentação do projeto.
* **Visual Studio Code:** ferramenta de edição de código, caso utilizada no desenvolvimento.

## ☁️ Integração com a Nuvem

A integração com a nuvem permite acompanhar os dados enviados pelo ESP32 durante a simulação.

Entre as informações que podem ser monitoradas estão:

* Distância medida pelo sensor ultrassônico.
* Porcentagem estimada de preenchimento da lixeira.
* Nível de ocupação identificado pelo sistema.
* Histórico das medições recebidas.

A comunicação pode ser realizada por HTTP ou MQTT, conforme a plataforma escolhida e sua configuração.

Para a conexão Wi-Fi simulada no Wokwi, utiliza-se:

* **SSID:** `Wokwi-GUEST`
* **Senha:** `""` (em branco)

A integração deve ser testada para verificar se os dados estão sendo recebidos e exibidos corretamente no dashboard.

## 💰 Viabilidade Financeira

A tabela abaixo apresenta valores estimados sugeridos para o levantamento inicial de custos. Os preços devem ser confirmados por meio de pesquisa em lojas de componentes eletrônicos.

| Componente                  |          Quantidade | Valor unitário estimado |
| --------------------------- | ------------------: | ----------------------: |
| ESP32 Wi-Fi/Bluetooth       |                   1 |                R$ 45,00 |
| Sensor ultrassônico HC-SR04 |                   1 |                R$ 12,00 |
| Fonte de alimentação 5 V    |                   1 |                R$ 25,00 |
| LEDs indicadores            |                   3 |             A pesquisar |
| Resistores                  | Conforme necessário |             A pesquisar |
| Protoboard e jumpers        | Conforme necessário |             A pesquisar |

**Custo total:** a calcular após a confirmação dos preços de todos os componentes.

Os valores apresentados são referências iniciais fornecidas no roteiro da atividade, não cotações comerciais verificadas. Os custos podem variar conforme a loja, a região e o frete.

## 🧪 Simulação no Wokwi

O Wokwi é utilizado para montar o circuito virtual, programar o ESP32 e testar o funcionamento do sensor e dos LEDs.

Durante a simulação, devem ser verificados:

* A leitura correta das distâncias.
* O cálculo da porcentagem de preenchimento.
* O acionamento dos LEDs conforme os limites definidos.
* A conexão Wi-Fi simulada.
* O envio dos dados para a plataforma de nuvem.


## 📊 Dashboard de Monitoramento

O dashboard é responsável por apresentar os dados recebidos do protótipo. Ele pode conter gráficos de variação do nível de preenchimento e indicadores com a ocupação atual da lixeira.

📸 **Comprovação da integração:** insira uma captura de tela do painel na nuvem mostrando os dados recebidos durante a simulação.

## 📚 Conceitos Aplicados

Durante o desenvolvimento do projeto, são trabalhados os seguintes conceitos:

* Internet das Coisas (IoT).
* Sensores e atuadores.
* Programação de microcontroladores.
* Leitura e processamento de dados.
* Comunicação Wi-Fi.
* Protocolos de comunicação HTTP ou MQTT.
* Integração com serviços de nuvem.
* Visualização de dados em dashboards.
* Pesquisa de componentes e estimativa de custos.
* Simulação de circuitos eletrônicos.

## 🌱 Benefícios da Solução

A Lixeira Inteligente apresenta benefícios potenciais para o gerenciamento de resíduos urbanos:

* Monitoramento do nível de preenchimento.
* Identificação de lixeiras que precisam de coleta.
* Possibilidade de otimizar rotas de coleta.
* Redução de deslocamentos desnecessários.
* Apoio ao planejamento da limpeza urbana.
* Aplicação prática dos conceitos de IoT em Smart Cities.

Esses benefícios dependem da implementação, da confiabilidade das medições e da integração efetiva com o sistema de coleta.

## 🎓 Sobre a Atividade

**Curso:** Técnico em Desenvolvimento de Sistemas
**Disciplina:** Fundamentos de IoT
**Projeto:** Desafio Prático — Desenvolvimento de Solução IoT Conectada à Nuvem
**Professor:** Denani
**Plataforma de prototipagem:** Wokwi Simulator

## 👨‍💻 Integrantes

* ARTHUR RIBEIRO DE AZEVEDO
* ANA PAULA LIMA FERREIRA
* QUEZIA DA PAZ BRITO SILVA
* OTHÁVIO KAUAN GOMES CORRÊA

## 📝 Conclusão

O projeto Lixeira Inteligente demonstra como a Internet das Coisas pode ser aplicada ao monitoramento de resíduos e ao desenvolvimento de soluções para cidades inteligentes.

Por meio da utilização do ESP32, do sensor ultrassônico, dos LEDs indicadores e da integração com uma plataforma de nuvem, a proposta permite acompanhar o nível estimado de preenchimento de uma lixeira e disponibilizar informações para apoiar o planejamento da coleta.

A atividade contribui para o aprendizado de programação embarcada, sensores, conectividade Wi-Fi, comunicação com serviços em nuvem e documentação de projetos tecnológicos.
