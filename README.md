# Geosense

### Rafael de Souza Pinto - RM 555130
### Luis Paulo Freitas Fernandes - RM 555497
### Enzo Marsola - RM 556310

Este projeto integra conceitos de **IoT (Internet das Coisas)**, **IoB (Internet of Behaviors)** e **IA Generativa** para realizar a **detecção inteligente de vagas de estacionamento** a partir de imagens processadas por visão computacional, com persistência de dados em banco Oracle e interface via terminal.

## 🧠 Visão Geral

O sistema utiliza uma imagem de estacionamento, onde o usuário calibra as vagas (áreas de interesse - ROIs). O sistema então detecta quais vagas estão **livres** ou **ocupadas** com base em análise de pixels escuros (thresholding). Os dados são armazenados em um banco de dados Oracle, com histórico e tempo médio de ocupação para análise comportamental (IoB). Possui potencial de expansão com IA generativa para simulação de cenários e predição de ocupação futura.

---

## 🚀 Tecnologias Utilizadas

| Tecnologia       | Finalidade                               |
|------------------|-------------------------------------------|
| Python 3.10+     | Lógica de detecção e orquestração geral   |
| OpenCV           | Processamento de imagem                   |
| Oracle DB        | Armazenamento de dados (status/histórico) |
| Colorama         | Feedback visual no terminal               |
| Matplotlib       | Visualização gráfica (tempo médio)        |
| Pickle           | Serialização das ROIs                     |

---

## 📸 Funcionalidades

- Calibração das vagas (seleção manual das ROIs)
- Detecção de vagas ocupadas/livres em imagem
- Registro histórico no banco de dados
- Visualização da imagem com status
- Tempo médio de ocupação por vaga (gráfico)
- Troca dinâmica da imagem em uso
---


## ⚙️ Instalação
```bash
pip install opencv-python
pip install oracledb
pip install colorama
pip install matplotlib
pip install numpy
```
## 🧠 Pré-requisitos
- Python 3.7+

- Conexão com a internet

- Conta de acesso ao Oracle:
  - Substitua no código:
      ```python
      ORACLE_USER     = "RMxxx"      # seu usuário
      ORACLE_PASSWORD = "xxxxx"      # sua senha
      ```

## 🗄️ Banco de Dados
Tabelas criadas automaticamente:

VAGAS_STATUS (VAGA_ID, STATUS, UPDATED_AT)

VAGAS_HISTORICO (ID, VAGA_ID, STATUS, TIMESTAMP)

CONFIG_IMAGEM (ID, IMAGEM_ATUAL)

## 📈 Resultados Parciais
Detecção visual de vagas com cores e texto (OpenCV)

Histórico de mudanças de estado por vaga

Cálculo automático do tempo médio de ocupação por vaga (IoB)

Interface de linha de comando interativa com feedback visual (Colorama)

## ▶️ Como Usar

1. Execute o script principal:

```bash
python deteccao.py
```

2- No menu interativo, siga as opções:

-  Calibrar Vagas: selecione manualmente as áreas de vaga na imagem.

-  Detectar Vagas: realiza a análise e desenha os retângulos verdes/vermelhos.

-  Mostrar Imagem Atual: exibe status atual das vagas.

-  Ver Tempo Médio: gráfico de média por vaga.

-  Trocar Imagem: altera a imagem em uso no sistema.
  
