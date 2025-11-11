# AeroFlyControl - Guia de Construção v1

> Projeto de aeromodelo controlado por rádio com sistema de estabilização automática

## 📋 Sobre o Projeto

O **AeroFlyControl** é um projeto educacional desenvolvido pelo grupo de pesquisa SETA (Sistemas Embarcados: Tecnologias e Aplicações) da Universidade Federal de Mato Grosso (UFMT). 

### Etapa 1 - Construção Física (v1)

Esta primeira etapa abrange a construção completa da fuselagem e a integração de todos os componentes de hardware, incluindo testes operacionais básicos usando rádio controle, como o acionamento dos servos motores dos flaps e do profundor.

---

## 🛩️ Modelo: Simple Stick Asa Alta

### Características Principais

- **Tipo:** Avião tradicional com motor dianteiro
- **Material:** Depron 5mm
- **Configuração:** Asa alta (estável e fácil de pilotar)
- **Vantagens:** Leve, resistente e com excelente manobrabilidade

### 📐 Plantas de Construção

Plantas disponíveis em: [Intermodel.fr](https://www.intermodel.fr/)

- **Parte 1:** Fuselagem e estrutura principal
- **Parte 2:** Asas e estabilizadores
- **Parte 3:** Detalhes e acabamentos

---

## 🔧 Lista de Componentes

### 1. Sistema de Propulsão

| Componente | Especificações | Função |
|------------|----------------|--------|
| **Motor BLDC** | A2212/6T<br>• Tensão: 6-12.6V<br>• Corrente: 1.8-22A<br>• Velocidade: 27.500rpm<br>• Potência: 150W<br>• Empuxo: 620g<br>• Peso: 52g<br>• Dimensões: Ø28mm x 26mm | Gerar propulsão através da hélice |
| **Hélice** | 8060 (8x6 polegadas)<br>• Material: Nylon reforçado com fibra de vidro<br>• Furo de montagem: 5mm<br>• Peso: 6g<br>• Cor: Preto | Converter rotação em empuxo |
| **ESC** | 40A<br>• Corrente contínua/pico: 40A/55A<br>• Bateria: 2-3S LiPo<br>• BEC: 5V, 3A (modo linear)<br>• Cabo: 16AWG<br>• Plugue: Tipo T | Controlar velocidade e rotação do motor |
| **Bateria** | LiPo 2200mAh, 3S, 11.1V | Alimentar todo o sistema |
| **Carregador** | Imax B3 Pro<br>• Entrada: AC 110-240V<br>• Corrente de balanceamento: 850mA<br>• Compatível: 2S-3S LiPo<br>• Display: LED verde/vermelho<br>• Peso: 180g | Carregar e balancear bateria LiPo |

### 2. Sistema de Controle

| Componente | Especificações | Função |
|------------|----------------|--------|
| **Rádio TX** | Flysky FS-i6X<br>• 10 canais, 2.4GHz<br>• Sistema: AFHDS2A | Transmitir comandos do piloto |
| **Receptor RX** | Flysky FS-iA6B<br>• Canais: 6CH<br>• Frequência: 2.4-2.48GHz<br>• Largura de banda: 140<br>• Potência TX: ≤20dBm<br>• Sensibilidade: -105dBm<br>• Codificação: GFSK<br>• Antena: Dupla 26mm<br>• Tensão: 4.0-6.5V DC<br>• Dimensões: 47x26.2x15mm<br>• Peso: 14.9g<br>• Interface: i-Bus e PPM<br>• Compatível: FS-i4, FS-i6, FS-i10 | Receber comandos e distribuir aos servos |
| **Controlador** | A3v2 (Giroscópio 3 eixos)<br>• Tensão: 5-7.4V (suporta HV)<br>• Giroscópio: ±2000 dps<br>• Acelerômetro: ±4g<br>• Frequências servo: 50Hz, 125Hz, 250Hz<br>• Viagem servo: 1520±500μs<br>• Dimensões: 43x27mm<br>• Material: ABS, PC<br>• **4 Modos de voo:** Normal, Auto-balanceamento, Auto-pairar, Girar<br>• **3 Tipos de asa:** Padrão, Delta, V-tail<br>• Funções: Salvamento automático, calibração automática | Estabilizar o voo automaticamente |
| **Servo Motor** | 9g (x3 unidades)<br>• Rotação: 180°<br>• Torque: 1.8kg/cm | Controlar superfícies de voo (ailerons, profundor, leme) |

### 3. Sistema Embarcado (Telemetria - v2)

| Componente | Especificações | Função |
|------------|----------------|--------|
| **ESP32** | • CPU: Xtensa LX6 32-bit (Single/Dual-core)<br>• Tensão: 3.3V<br>• I/O Digital: 25 pinos<br>• Entrada Analógica: 6 pinos<br>• Saída Analógica: 2 pinos<br>• UART: 3, SPI: 2, I2C: 3<br>• Flash: 4MB, SRAM: 520KB<br>• Clock: 240MHz<br>• Wi-Fi: IEEE 802.11 b/g/n/e/i | Processamento e comunicação wireless |
| **BMP280** | • Faixa: 300-1100 hPa<br>• Precisão relativa: ±0.12 hPa (≈±1m)<br>• Precisão absoluta: ±1 hPa<br>• Temperatura: -40 a +85°C<br>• Interface: I2C (até 3.4MHz), SPI (até 10MHz)<br>• Consumo: 2.7μA @ 1Hz | Sensor de pressão e altitude |

### 4. Estrutura e Fixação

| Componente | Material | Função |
|------------|----------|--------|
| **Fuselagem** | Depron 5mm | Corpo principal da aeronave |
| **Reforços** | Vareta de fibra 2.0mm | Estrutura interna de sustentação |
| **Trem de Pouso** | PLA HT (impresso 3D) | Suporte para decolagem/pouso |
| **Bico** | PLA HT (impresso 3D) | Proteção e fixação do motor |
| **Dobradiças** | Nylon | Articulação de superfícies móveis |
| **Chifres e Clevis** | Nylon | Conexão servo-superfície de controle |

---

## 📍 Layout dos Componentes

```
┌─────────────────────────────────────────────────┐
│                   NARIZ                         │
│  [Bico PLA] ──► Motor BLDC A2212/6T + Hélice   │
│                 (52g + 6g)                      │
├─────────────────────────────────────────────────┤
│                   FRONTAL                       │
│  • ESC 40A (com BEC 5V/3A)                     │
│  • Controlador A3v2 (giroscópio + acelerômetro)│
│    - 4 modos de voo                            │
│    - Calibração automática                     │
├─────────────────────────────────────────────────┤
│                   CENTRO (CG)                   │
│  • Bateria LiPo 3S 2200mAh 11.1V               │
│  • Receptor FS-iA6B (14.9g)                    │
│    - 6 canais                                  │
│    - Interface i-Bus/PPM                       │
├─────────────────────────────────────────────────┤
│                   ASAS                          │
│  • Servos 9g (x2) - Ailerons                   │
│    - Torque: 1.8kg/cm                          │
├─────────────────────────────────────────────────┤
│                   CAUDA                         │
│  • Servo 9g (x1) - Profundor/Leme             │
│                                                 │
└─────────────────────────────────────────────────┘
```

### Distribuição de Peso

- **Frente (30%):** Motor (52g), ESC, bico
- **Centro (50%):** Bateria, receptor (14.9g), controlador
- **Cauda (20%):** Servos, estrutura traseira

> ⚠️ **Importante:** O centro de gravidade (CG) deve estar localizado aproximadamente a 1/3 da corda da asa a partir do bordo de ataque.

---

## 🔌 Diagrama de Conexões

```
                    [Bateria LiPo 3S 11.1V]
                            |
                    ┌───────┴───────┐
                    |               |
                [ESC 40A]      [Receptor FS-iA6B]
                    |               |
            [Motor BLDC]    ┌───────┼───────┬───────┐
                            |       |       |       |
                      [A3v2] [Servo1] [Servo2] [Servo3]
                    Estabilizador
                    
BEC 5V/3A do ESC ──► Alimenta Receptor + Controlador + Servos
```

### Conexões do Receptor FS-iA6B

- **Canal 1:** Aileron (Servo 1)
- **Canal 2:** Profundor (Servo 2)
- **Canal 3:** Acelerador (ESC)
- **Canal 4:** Leme (Servo 3)
- **Canal 5-6:** Funções auxiliares
- **i-Bus:** Conexão com A3v2 para estabilização

---

## ⚙️ Modos de Voo do A3v2

### 1. Normal
- Controle manual completo
- Sem estabilização

### 2. Auto-balanceamento
- Estabilização automática de atitude
- Retorna à posição nivelada ao soltar comandos

### 3. Auto-pairar
- Mantém altitude e posição
- Ideal para voo estacionário

### 4. Girar
- Facilita manobras acrobáticas
- Taxa de rotação otimizada

---

## ✅ Testes Realizados na v1

- [x] Conexão rádio TX (FS-i6X) / RX (FS-iA6B)
- [x] Verificação de alcance e qualidade do sinal 2.4GHz
- [x] Acionamento dos servos motores (torque 1.8kg/cm)
- [x] Teste de movimento dos ailerons (Servo 1 e 2)
- [x] Teste de movimento do profundor (Servo 3)
- [x] Teste de movimento do leme
- [x] Verificação do ESC 40A e motor BLDC
- [x] Teste de rotação da hélice 8060
- [x] Verificação do BEC 5V/3A
- [x] Configuração do controlador A3v2
- [x] Teste dos 4 modos de voo
- [x] Calibração automática do giroscópio
- [x] Teste da interface i-Bus

---

## 🔋 Cuidados com a Bateria LiPo

### Carregamento
- Usar sempre o Imax B3 Pro
- Carregar em modo balanceado (850mA)
- Não deixar desacompanhado durante carga
- Carregar em superfície não inflamável

### Armazenamento
- Tensão de armazenamento: 3.8V por célula (11.4V total)
- Local fresco e seco
- Usar bolsa LiPo à prova de fogo

### Descarte
- Nunca descartar no lixo comum
- Descarregar completamente em água salgada
- Levar a pontos de coleta especializados

---

## 🚀 Próximas Etapas (v2)

A segunda etapa do projeto focará em:

- Integração do ESP32 para telemetria
- Implementação do sensor BMP280 para altitude
- Sistema de logging de dados via Wi-Fi
- Interface web para monitoramento em tempo real
- Otimização do sistema de estabilização A3v2
- Testes de voo e ajustes finos de CG
- Implementação de modos automáticos avançados

---

## 📊 Especificações Técnicas Resumidas

| Parâmetro | Valor |
|-----------|-------|
| Envergadura | ~800mm (conf. planta) |
| Peso total estimado | ~450g |
| Empuxo motor | 620g |
| Relação peso/potência | 1.38:1 |
| Autonomia estimada | 10-15 min |
| Velocidade máxima | ~60 km/h |
| Alcance rádio | ~500m |
| Canais de controle | 6 |
| Sistema de estabilização | 3 eixos |

---

## 📚 Referências

- **Plantas:** [Intermodel.fr](https://www.intermodel.fr/)
- **Instituição:** Universidade Federal de Mato Grosso (UFMT)
- **Grupo de Pesquisa:** SETA - Sistemas Embarcados: Tecnologias e Aplicações
---

## 📝 Licença

Este projeto é de caráter educacional e está disponível para fins acadêmicos.

---

## 👥 Contribuidores

Desenvolvido pelo grupo SETA - UFMT

---

## ⚠️ Avisos de Segurança

- Sempre remover a hélice durante testes de bancada
- Manter distância segura durante testes com motor ligado
- Usar óculos de proteção
- Verificar todas as conexões antes de cada voo
- Voar em área aberta e longe de pessoas
- Respeitar regulamentação local para aeromodelos

---

## 📧 Contato

Para mais informações sobre o projeto, entre em contato com o grupo de pesquisa SETA/UFMT.
