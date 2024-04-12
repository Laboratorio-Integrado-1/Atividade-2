# Atividade 2: Controlador de Robô para Remoção de Detritos em Tubulação
## UNIVERSIDADE FEDERAL DA BAHIA – UFBA
### ESCOLA POLITÉCNICA / DEPARTAMENTO DE ENGENHARIA ELÉTRICA E DE COMPUTAÇÃO
#### ENGG52 – LABORATÓRIO INTEGRADO I-A – 2024.1
#### Wagner Luiz Alves de Oliveira

## Equipe

- Felipe Soares Trebino
- Fabio Miguel Mascarenhas dos Santos
- Marcio Gabriel Alves Trindade

## Especificação do Problema

O objetivo desta atividade é projetar e simular um controlador para um robô autônomo que opera dentro de uma tubulação metálica. O robô é projetado para identificar e remover detritos não metálicos que obstruem a tubulação. A complexidade do ambiente da tubulação, que inclui múltiplas bifurcações e diferentes orientações de células (representadas em cinza no esquema da tubulação), desafia o robô a tomar decisões inteligentes sobre quando e como avançar, rotacionar ou remover entulhos.

## Especificações Técnicas
Sensores do Robô:
- Head (H): Detecta a presença de metal ou obstruções à frente.
- Left (L): Identifica aberturas livres à esquerda.
- Under (U): Sensor de chão que confirma se o robô está sobre um ponto de acesso (célula preta).
- Barrier (B): Detecta entulho removível à frente do robô.

Movimentos do Robô:
- Avançar (F): Move-se para frente se a célula à frente estiver livre.
- Rotacionar (T): Gira 90º para a esquerda dentro da mesma célula.
- Removendo Entulho (R): O robô ativa o mecanismo de remoção de detritos quando detecta um bloqueio composto por entulho removível.

## Estratégia de Desenvolvimento
A construção da máquina de estados finitos (FSM) seguiu uma abordagem sistemática:

### Identificação dos Estados:
- Avançando
- Stand-By
- Rotacionando
- Removendo Entulho
- Intermediário

### Tabela de Transições de Estados:
Foi elaborada uma tabela detalhada mapeando estados atuais, entradas sensoriais, estados futuros e saídas para definir a lógica de transição. Podemos ver um recorte da mesma na figura 1.

![Figura 1. Recorte da Tabela de Transições](https://github.com/Laboratorio-Integrado-1/Atividade-2/blob/main/Recorte%20da%20tabela%20de%20estados.png)

A tabela completa esta disponível a partir deste link : https://docs.google.com/spreadsheets/d/1M3G7sAugRDaKeGSTTQ3ImHe-3KtkDvaiJmCjNTxymsU/edit?usp=sharing

Ela tambem esta disponível no repositório: https://github.com/Laboratorio-Integrado-1/Atividade-2/blob/main/Atividade%202%20(Lab%201)%20-%20Diagrama%20de%20Estados.xlsx

### Diagrama de Estados: 
A partir da tabela, foi criado um diagrama de estados utilizando a abordagem de Mealy, onde as saídas dependem do estado atual e das entradas.

![Figura 2. Diagrama de estados](https://github.com/Laboratorio-Integrado-1/Atividade-2/blob/main/Diagrama%20LAB1%20-%20Atv%202.png)

### Simulação e Testes
Foi realizada uma simulação com 22 pulsos de clock para demonstrar o funcionamento do robô sob condições controladas, permitindo a verificação da eficácia da FSM projetada. O mapa utilizado para realização dos testes e exercícios se encontra abaixo em conjunto com a figura da Tabela de Simulações.

![Figura 3. Mapa Exemplo](https://github.com/Laboratorio-Integrado-1/Atividade-2/blob/main/Mapa%20Exemplo%20-%20Atividade%202.jpg)
![Figura 4. Tabela de simulações](https://github.com/Laboratorio-Integrado-1/Atividade-2/blob/main/Tabela%20de%20simulacao.png)

## Conclusões
O design da FSM provou ser eficaz na navegação e na limpeza de uma tubulação complexa. O robô conseguiu gerenciar eficientemente as tarefas de limpeza, priorizando movimentos estratégicos e adaptações conforme necessário, garantindo uma operação autônoma otimizada.