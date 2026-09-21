# TCC-CApA 2026 — Detecção e Classificação de Drones

Repositório desenvolvido como parte do Trabalho de Conclusão de Curso:

**Detecção e Classificação de Drones Utilizando Inteligência Artificial**

O trabalho é composto por duas etapas principais:

1. **Detecção de drones**, utilizando YOLO11n;
2. **Classificação visual do modelo do drone**, utilizando DenseNet201.

O objetivo deste repositório é disponibilizar os códigos, modelos treinados e procedimentos necessários para consulta e reprodução dos experimentos realizados.


---

## 1. Colab para treinamento dos modelos de IA

### 1.1 Classificação — DenseNet201

A etapa de classificação utiliza uma rede **DenseNet201**, pré-treinada no ImageNet e posteriormente treinada para classificação de quatro classes:

- DJI Inspire;
- DJI Mavic;
- DJI Phantom;
- No Drone.

O treinamento utiliza o **Cranfield Synthetic Drone Classification Dataset**.

O notebook contém:

- configuração automática do ambiente;
- download dos datasets;
- pré-processamento das imagens;
- treinamento incremental em 10, 20 e 50 épocas;
- armazenamento de checkpoints;
- métricas de validação;
- curvas de treinamento e validação;
- matrizes de confusão;
- avaliação em imagens reais do Anti-UAV;
- análise específica da classe DJI Mavic.

**Google Colab — Treinamento da classificação:**  
[ADICIONAR AQUI O LINK DO COLAB DE CLASSIFICAÇÃO]


### 1.2 Detecção — YOLO11n

A etapa de detecção utiliza o modelo **YOLO11n**, treinado para localizar drones em imagens.

O conjunto de dados utilizado nessa etapa é o **DUT Anti-UAV**.

O notebook contendo a preparação do ambiente, treinamento, validação e avaliação do modelo de detecção será disponibilizado nesta seção.

**Google Colab — Treinamento da detecção:**  
*Em preparação.*


---

## 2. Modelos de IA treinados

Os melhores modelos obtidos durante os experimentos são disponibilizados para permitir a execução dos testes sem a necessidade de realizar novamente todo o treinamento.


### 2.1 Modelo de classificação — DenseNet201

Modelo correspondente ao melhor resultado obtido durante o treinamento de classificação.

- **Arquitetura:** DenseNet201
- **Dataset de treinamento:** Cranfield Synthetic Drone Classification Dataset
- **Número máximo de épocas:** 50
- **Melhor época:** 48
- **Accuracy de validação:** 98,62%
- **Classes:** DJI Inspire, DJI Mavic, DJI Phantom e No Drone

**Download do modelo treinado:**

https://drive.google.com/file/d/1ikQihidPJ0wT09aa_-MEsNj0gryXJRoe/view?usp=sharing


### 2.2 Modelo de detecção — YOLO11n

O modelo de detecção foi treinado utilizando o conjunto de dados DUT Anti-UAV.

O melhor checkpoint (`best.pt`) será disponibilizado após a conclusão da migração da etapa de detecção para o Google Colab.

**Download do modelo treinado:**  
*Em preparação.*


---

## 3. Colab para importação dos modelos e realização dos testes

Além dos notebooks utilizados para treinamento, serão disponibilizados notebooks destinados exclusivamente à utilização dos modelos já treinados.

Esses notebooks permitem importar os pesos dos modelos e executar os testes sem necessidade de realizar novamente o processo completo de treinamento.


### 3.1 Teste do modelo de classificação

O notebook de teste deverá:

1. configurar o ambiente;
2. importar o modelo DenseNet201 treinado;
3. carregar os pesos correspondentes ao melhor modelo;
4. preparar as imagens de teste;
5. executar a classificação;
6. apresentar as classes estimadas e as métricas correspondentes.

**Google Colab — Teste da classificação:**  
[ADICIONAR AQUI O LINK DO COLAB DE TESTE DA CLASSIFICAÇÃO]


### 3.2 Teste do modelo de detecção

O notebook de teste da detecção permitirá carregar diretamente o modelo YOLO11n treinado e realizar inferência em imagens ou vídeos.

**Google Colab — Teste da detecção:**  
*Em preparação.*


---

## 4. Instruções de utilização

Este repositório foi organizado para permitir dois modos de utilização.


### Consulta dos resultados

Para consultar os resultados obtidos no trabalho, não é necessário realizar novamente todo o treinamento dos modelos.

Os notebooks e arquivos disponibilizados permitem recuperar:

- modelos treinados;
- checkpoints;
- históricos de treinamento;
- métricas;
- curvas de treinamento e validação;
- matrizes de confusão;
- resultados das avaliações realizadas.

Dessa forma, os resultados experimentais podem ser analisados diretamente.


### Reprodução dos experimentos

Caso seja desejado reproduzir os experimentos desde o início, devem ser utilizados os notebooks de treinamento disponibilizados na **Seção 1**.

Esses notebooks contêm todas as etapas necessárias para:

1. preparação do ambiente;
2. obtenção e organização dos dados;
3. pré-processamento;
4. configuração dos modelos;
5. treinamento;
6. validação;
7. armazenamento dos checkpoints;
8. avaliação dos resultados.


### Utilização dos modelos já treinados

Caso o objetivo seja apenas utilizar os modelos sem repetir o treinamento, recomenda-se utilizar os notebooks apresentados na **Seção 3**.

O fluxo de utilização é:

```text
Modelo treinado
      ↓
Importação dos pesos
      ↓
Imagem ou vídeo de entrada
      ↓
Inferência
      ↓
Resultado
