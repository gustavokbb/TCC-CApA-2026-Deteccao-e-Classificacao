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

O notebook contém todo o processo de treinamento, validação e avaliação do classificador.

Também permite consultar os resultados previamente obtidos sem executar novamente o treinamento.

**Google Colab — Treinamento da classificação:**  

https://colab.research.google.com/drive/1UUOj2rswcxfI5UP6A9vSz9hZyWhoKiS0?usp=sharing

### 1.2 Detecção — YOLO11n

A etapa de detecção utiliza o modelo **YOLO11n**, treinado para localizar drones em imagens.

O conjunto de dados utilizado nessa etapa é o **DUT Anti-UAV**.

O notebook contendo a preparação do ambiente, treinamento, validação e avaliação do modelo de detecção será disponibilizado nesta seção.

**Google Colab — Treinamento da detecção:**

https://colab.research.google.com/drive/13uvSsSTXOVH8RV0YJhlSzJR0sGPlGIk_?usp=sharing

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

## 3. Importação do modelo treinado e realização dos testes

O mesmo notebook de classificação também permite carregar o melhor modelo previamente treinado e acessar diretamente as etapas de validação e teste, sem repetir o treinamento.

Para esse modo de utilização:

1. execute a seção de configuração do ambiente;
2. não execute novamente as células de treinamento;
3. acesse diretamente as seções de resultados, validação e avaliação com dados reais.

**Google Colab — Teste da classificação:**  

https://colab.research.google.com/drive/1UUOj2rswcxfI5UP6A9vSz9hZyWhoKiS0?usp=sharing

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

Caso o objetivo seja apenas utilizar os modelos sem repetir o treinamento, recomenda-se visualizar as instruções apresentadas na **Seção 3**.

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
