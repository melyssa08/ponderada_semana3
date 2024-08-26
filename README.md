## Visão Geral do Projeto

Este repositório contém a implementação e análise de dois modelos diferentes de Entendimento de Linguagem Natural (NLU) usando redes neurais:

1. **Classificação de Intenções baseada em Word2Vec**: Implementa um modelo Word2Vec para criar embeddings de palavras e utiliza esses embeddings para classificar intenções de usuários.
2. **NLU & Redes Neurais**: Implementa uma rede neural para classificação de intenções usando uma camada de embedding e análise adicional com TensorFlow/Keras.

---

## 1. Classificação de Intenções baseada em Word2Vec

### Dependências

- Bibliotecas Python: `os`, `logging`, `zipfile`, `requests`, `numpy`, `pandas`, `sklearn`, `keras`, `matplotlib`, `gensim`
- Certifique-se de que todas as dependências estejam instaladas antes de executar o notebook.

### Módulo do Modelo Word2Vec

O modelo Word2Vec é encapsulado em uma classe chamada `Word2VecModel`. Esta classe inclui métodos para baixar, carregar e interagir com o modelo Word2Vec, incluindo:
- Carregamento de um modelo Word2Vec pré-treinado.
- Recuperação de vetores para palavras específicas.
- Encontrar as palavras mais similares.
- Exibição das palavras mais similares.

### Exemplos de Saídas

- **Tamanho do Vocabulário**: O tamanho do vocabulário do modelo foi testado e é equivalente ao número de palavras únicas na lista de vocabulário fornecida.
- **Palavras Mais Similares**: O modelo pode identificar e exibir as palavras mais similares a uma dada palavra, junto com suas pontuações de similaridade.
- **Embeddings de Sentenças**: O modelo calcula o embedding de uma sentença ao fazer a média dos vetores das palavras na sentença.

### Classificação com Rede Neural

- **Preparação dos Dados**: Os dados de texto processados foram transformados em embeddings usando o modelo Word2Vec. Esses embeddings foram então utilizados como entrada para uma rede neural.
- **Arquitetura do Modelo**: A rede neural consiste em três camadas: uma camada de entrada, duas camadas ocultas com ativação `ReLU`, e uma camada de saída com ativação `softmax` para classificação multi-classe.
- **Treinamento & Avaliação**: O modelo foi treinado em 80% dos dados e testado em 20%. A acurácia final obtida foi **88,61%** no conjunto de teste .

---

## 2. NLU & Redes Neurais (sem3-nlu-nn.ipynb)

### Equipe do Projeto

Este projeto foi realizado como parte de uma atividade em sala de aula com os seguintes participantes:
- Allan Casado
- Cristiane Andrade
- Elias Biondo
- Giovana Thomé
- Melyssa Rojas
- Rafael Cabral

### Importação e Pré-processamento de Dados

- **Conjunto de Dados**: O conjunto de dados utilizado consiste em consultas de usuários pré-processadas com intenções correspondentes.
- **Codificação de Labels**: Intenções únicas foram extraídas e codificadas em rótulos inteiros para uso no modelo de rede neural.

### Modelo de Rede Neural

- **Arquitetura do Modelo**: 
  - **Camada de Embedding**: Mapeia palavras para um espaço vetorial denso.
  - **Camada Flatten**: Converte a saída 2D da camada de embedding em um vetor 1D.
  - **Camadas Densas**: Inclui uma camada oculta com ativação `ReLU` e uma camada de saída com ativação `softmax` para classificação multi-classe.

### Treinamento & Avaliação

- **Divisão de Dados**: Inicialmente, os dados foram divididos incorretamente, levando a resultados ruins. Isso foi corrigido com uma divisão aleatória, melhorando significativamente a acurácia do modelo.
- **Resultados do Treinamento**: O modelo foi treinado por 100 épocas. A acurácia final no conjunto de teste, após a correção da divisão dos dados, foi de **82,24%**【15:10†source】.

### Observações

- **Problema Inicial no Treinamento**: A primeira execução do treinamento resultou em uma acurácia muito baixa devido à divisão incorreta dos dados (divisão não aleatória baseada em categorias). Após corrigir isso, o modelo mostrou um desempenho muito melhor.
- **Desempenho do Modelo**: O modelo alcançou uma acurácia de teste de **82,24%**, refletindo uma boa generalização para dados não vistos após a correção do problema inicial.

---

## Conclusão

Demonstramos a implementação de duas abordagens diferentes para a classificação de intenções em tarefas de NLU. O modelo baseado em Word2Vec aproveita efetivamente os embeddings pré-treinados, enquanto a abordagem NLU & Redes Neurais demonstra a importância do manuseio adequado dos dados e da arquitetura do modelo para alcançar um bom desempenho.

Ambos os modelos oferecem insights valiosos e podem ser ainda mais otimizados com ajustes de hiperparâmetros e técnicas avançadas, como aumento de dados e regularização.

---

Consulte os notebooks individuais (`sem3-nlu-nn.ipynb` e `Word2Vec.ipynb`) para a implementação detalhada do código e mais informações.

---