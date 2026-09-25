# My First Neural Network 🧠

Rede neural simples em **JavaScript** com **TensorFlow.js** que classifica pessoas em três categorias (`premium`, `medium`, `basic`) a partir de idade, cor preferida e localização.

> **EN:** A minimal TensorFlow.js neural network (Node.js) that classifies people into three tiers using normalized and one-hot encoded features.

## O que o projeto demonstra

- **Pré-processamento de dados:** normalização min-max da idade e *one-hot encoding* de atributos categóricos (cor e cidade).
- **Modelo sequencial:** camada densa oculta (80 neurônios, ReLU) + camada de saída com **softmax** para 3 classes.
- **Treino:** otimizador **Adam**, função de perda `categoricalCrossentropy`, 100 épocas com *shuffle*.
- **Inferência:** conversão de um novo registro em tensor e retorno das probabilidades de cada classe, ordenadas.

## Stack

| Tecnologia | Uso |
|---|---|
| Node.js (ES Modules) | Execução do script |
| @tensorflow/tfjs 4.x | Criação, treino e predição do modelo |

## Como executar

```bash
git clone https://github.com/JessicaGPW/my-first-neural.git
cd my-first-neural
npm install
npm start        # roda em modo --watch
```

Saída esperada (os valores variam a cada treino):

```
premium (xx.xx%)
medium (xx.xx%)
basic (xx.xx%)
```

## Como funciona

```
[idade_norm, azul, vermelho, verde, São Paulo, Rio, Curitiba]
        │
   Dense(80, relu)
        │
   Dense(3, softmax)  →  [premium, medium, basic]
```

1. Os dados de treino ficam em `index.js` já normalizados.
2. `trainModel()` cria e treina o modelo.
3. `predict()` recebe uma nova pessoa normalizada e devolve as probabilidades.

## Próximos passos

- [ ] Gerar a normalização e o one-hot automaticamente a partir dos objetos brutos
- [ ] Aumentar o dataset e separar treino / validação
- [ ] Exibir a curva de *loss* e *accuracy* por época
- [ ] Salvar e recarregar o modelo treinado (`model.save`)

## Autora

**Jessica Baptista** · [GitHub](https://github.com/JessicaGPW) · [LinkedIn](https://www.linkedin.com/in/baptistajessica/)
