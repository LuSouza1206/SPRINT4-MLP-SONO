# Sprint 4 — CNN
## Classificação de Ambientes por Imagem com Rede Neural Convolucional

Disciplina: Inteligência Artificial — FIAP

---

## Integrantes

| Nome | RM |
|------|----|
| Kaio Vinicius Meireles Alves | RM553282 |
| Lucas Alves de Souza | RM553956 |
| Lucas de Freitas Pagung | RM553242 |
| Guilherme Fernandes de Freitas | RM554323 |
| João Pedro Chizzolini de Freitas | RM553172 |

---

## Objetivo

Desenvolver uma CNN capaz de classificar imagens de ambientes residenciais em 5 categorias, integrando visão computacional ao app de saúde digital desenvolvido ao longo dos sprints anteriores.

---

## Problema

Dada uma imagem de um ambiente interno, o modelo identifica o tipo de cômodo presente. No contexto do app, isso permite detectar se o usuário está no quarto (ambiente adequado para dormir) antes do horário de descanso, gerando alertas personalizados.

---

## Dataset

**House Rooms Image Dataset** — Kaggle  
https://www.kaggle.com/datasets/robinreni/house-rooms-image-dataset

| Classe | Imagens |
|--------|---------|
| Bathroom | 606 |
| Bedroom | 1.248 |
| Dinning | 1.158 |
| Kitchen | 965 |
| Livingroom | 1.273 |
| **Total** | **5.251** |

---

## Modelo

- **Arquitetura:** MobileNetV2 com transfer learning (pesos ImageNet)
- **Camadas adicionais:** GlobalAveragePooling2D → Dense(128, ReLU) → Dropout(0.3) → Dense(5, Softmax)
- **Otimizador:** Adam
- **Loss:** Categorical Crossentropy
- **Callbacks:** EarlyStopping + ReduceLROnPlateau

---

## Resultados

| Métrica | Valor |
|---------|-------|
| Acurácia (validação) | 78,24% |
| Loss (validação) | 0,5790 |
| Melhor época | 7 |
| Épocas executadas | 12 (early stopping) |

---

## Como Executar

1. Abrir `sprint4_cnn.ipynb` no Google Colab
2. Inserir as credenciais do Kaggle na célula 2
3. Executar todas as células em ordem

---

## Estrutura do Repositório

```
sprint4/
├── sprint4_cnn.ipynb
├── Sprint4_CNN.docx
└── README.md
```
