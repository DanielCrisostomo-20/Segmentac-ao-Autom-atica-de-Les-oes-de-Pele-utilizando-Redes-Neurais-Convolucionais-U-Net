# Segmentação Automática de Lesões de Pele utilizando Redes Neurais Convolucionais U-Net

Este projeto implementa um modelo de **segmentação de imagens médicas** para identificar automaticamente lesões de pele a partir de imagens dermatoscópicas, utilizando a arquitetura **U-Net** com **TensorFlow/Keras**.

O trabalho foi desenvolvido como parte de um estudo de Inteligência Artificial aplicado à área da saúde, com foco na segmentação semântica de lesões do dataset **ISIC 2018**.

---

## Objetivo

O objetivo principal é treinar uma rede U-Net capaz de:

- localizar regiões de lesões de pele em imagens médicas;
- gerar máscaras de segmentação binárias;
- avaliar o desempenho por meio de métricas como:
  - **Dice Coefficient**
  - **IoU (Intersection over Union)**
  - **Precision**
  - **Recall / Sensitivity**
  - **Specificity**

---

## Tecnologias Utilizadas

- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- OpenCV
- Scikit-learn
- KaggleHub
- Jupyter Notebook / Google Colab

---

## Estrutura do Projeto

O projeto está concentrado principalmente no notebook:

- `trabalho_final_de_IA.ipynb`

Neste notebook estão implementados:

- definição da arquitetura U-Net;
- funções de perda e métricas;
- pré-processamento de imagens e máscaras;
- carregamento do dataset ISIC;
- treinamento e validação do modelo;
- visualização dos resultados.

---

## Dataset

Foi utilizado o conjunto de dados **ISIC 2018 Task 1** para segmentação de lesões de pele.

Dataset utilizado via KaggleHub:

- `tschandl/isic2018-challenge-task1-data-segmentation`

As imagens originais e máscaras foram redimensionadas para:

- **256 x 256 pixels**

---

## Arquitetura do Modelo

A rede utilizada é uma **U-Net clássica**, composta por:

- **Encoder**: camadas convolucionais e pooling para extração de características;
- **Bottleneck**: camada intermediária com maior profundidade;
- **Decoder**: upsampling por convolução transposta;
- **Skip Connections**: preservação de detalhes espaciais entre encoder e decoder.

A saída final é uma máscara binária com ativação **sigmoid**.

---

## Função de Perda

O projeto compara abordagens de perda para segmentação desbalanceada:

- **Binary Crossentropy**
- **Dice Loss**
- **BCE + Dice Loss**

A combinação **BCE + Dice Loss** é usada para melhorar a segmentação de regiões pequenas e lidar melhor com o desbalanceamento entre fundo e lesão.

---

## Métricas

As métricas implementadas para avaliação foram:

- **Dice Coefficient**
- **IoU**
- **Precision**
- **Recall**
- **Specificity**

---

## Pré-processamento

As imagens e máscaras passam pelas seguintes etapas:

1. leitura dos arquivos;
2. conversão para o formato adequado;
3. redimensionamento para `256x256`;
4. normalização dos valores entre `0` e `1`.

---

## Resultados

O notebook apresenta:

- comparação entre funções de perda;
- curva de treinamento;
- visualização de máscaras reais e predições do modelo;
- avaliação final no conjunto de validação.

Exemplo de métricas obtidas no experimento:

- **Loss**: 0.5040
- **Dice Coefficient**: 0.7718
- **IoU**: 0.6845
- **Precision**: 0.9673
- **Sensitivity**: 0.6989
- **Specificity**: 0.9900

> Observação: esses valores podem variar conforme a execução, o subconjunto de dados utilizado e as condições de treinamento.

---

## Como Executar

### 1. Clonar o repositório

```bash
git clone https://github.com/DanielCrisostomo-20/Segmentac-ao-Autom-atica-de-Les-oes-de-Pele-utilizando-Redes-Neurais-Convolucionais-U-Net.git
cd Segmentac-ao-Autom-atica-de-Les-oes-de-Pele-utilizando-Redes-Neurais-Convolucionais-U-Net
