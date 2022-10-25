# cbis_covid  😷


📌 Trata-se de repositório para os códigos utilizados no trabalho "Identificação automática do uso de máscaras de proteção facial: um estudo comparativo".
O trabalho foi apresentado no XIX Congresso Brasileiro de Informática em Saúde (CBIS - 2022).

✏️  Maiores explicações sobre a metodologia utilizada podem ser obtidas no referido artigo.

### 🎓 Como citar🎓 

```
@INPROCEEDINGS{227172,
    AUTHOR="José Luiz Neves Voltan and Ronaldo Goldschmidt and Jefferson Oliva and Julio Duarte and Dalcimar Casanova and Marcelo Teixeira",
    TITLE="Identificação automática do uso de máscaras de proteção facial: um estudo comparativo",
    BOOKTITLE="CBIS-2022 () ",
    ADDRESS="",
    DAYS="29-2",
    MONTH="nov",
    YEAR="2022",
    ABSTRACT="Objetivo: O uso de máscaras de proteção é uma importante medida para diminuir a transmissão da COVID-19 e de outras doenças. O presente trabalho teve como objetivo realizar um estudo comparativo entre diferentes modelos de aprendizado profundo aplicados na identificação da máscara de proteção (pessoa sem máscara, com máscara ou com máscara incorretamente posicionada). Métodos: foram implementados e avaliados os modelos de Redes Neurais Convolucionais MobileNetV3, Xception, VGG19. Foi utilizada a técnica de transferência de aprendizado na implementação e ajuste desses modelos. Resultados: Os modelos avaliados apresentaram acurácias que variaram entre 42% e 86%, esta última obtida pelo modelo Xception, superando os resultados reportados na literatura correlata. Conclusão: Os resultados apontam para o potencial promissor do modelo Xception que, ao viabilizar o monitoramento automático, permite a orientação de pessoas quanto ao correto uso de máscaras de proteção, dessa forma, contribuindo para diminuir o espalhamento de doenças através das vias aéreas. Descritores: Máscara de Proteção; Aprendizado de Máquina; Redes Neurais Convolucionais",
    KEYWORDS="1. Tópico Especial: Sistemas Inteligentes para Saúde; 3. Processamento de sinais e imagens para saúde",
    URL="http://XXXXX/227172.pdf"
}
```

_Obs.: Aguardando complementação_


### 📝 Resumo do trabalho 📝
Objetivo: O uso de máscaras de proteção é uma importante medida para diminuir a transmissão da COVID-19 e de outras doenças. O presente trabalho teve como objetivo realizar um estudo comparativo entre diferentes modelos de aprendizado profundo aplicados na identificação da máscara de proteção (pessoa sem máscara, com máscara ou com máscara incorretamente posicionada). Métodos: foram implementados e avaliados os modelos de Redes Neurais Convolucionais MobileNetV3, Xception, VGG19. Foi utilizada a técnica de transferência de aprendizado na implementação e ajuste desses modelos. Resultados: Os modelos avaliados apresentaram acurácias que variaram entre 42% e 86%, esta última obtida pelo modelo Xception, superando os resultados reportados na literatura correlata. Conclusão: Os resultados apontam para o potencial promissor do modelo Xception que, ao viabilizar o monitoramento automático, permite a orientação de pessoas quanto ao correto uso de máscaras de proteção, dessa forma, contribuindo para diminuir o espalhamento de doenças através das vias aéreas.

Descritores: Máscara de Proteção; Aprendizado de Máquina; Redes Neurais Convolucionais

### 💬 Breve explicação 💬
- Buscamos deixar os _notebooks_ comentados com o máximo de explicações e sugestões de leituras complementares no que se refere ao processo de codificação;
- No código, foi utilizado GPU, com a finalidade de diminuir o tempo de treinamento da Rede Neural Convolucional (CNN). Deve-se ter especial atenção à sua configuração;
- Perceba que o dataset de treino (treino+validação) encontra-se no diretório ```D:/TCC/1/p1 ``` , enquanto o dataset de teste está em ```D:/artigo/mix ``` . Você pode alterar isso, lembre-se de editar a célula correspondente.
- Para a arquitetura simples (A, B, C, D), observe o tópico ``` Hiper-parâmetros ```
    - vale lembrar a codificação adotada: (A) representa o modelo com 3 canais e não normalizado, (B) o modelo em escala cinza e não normalizado, (C) com 3 canais e normalizado, e por fim (D) em escala cinza e normalizado.
- Quanto aos modelos que utilizaram transferência de aprendizado, MobileNetV3Large, Xception e VGG19, as abordagens foram:

    (I) - o núcleo foi congelado, isto é, não teve seus pesos e parâmetros ajustados durante o treinamento. 
    
    (II) - o núcleo também foi congelado para um treinamento inicial. Foi realizado um treinamento inicial. Depois disso, o núcleo foi descongelado, e todo modelo foi treinado novamente. Perceba que ocorreram variações nos parâmetros de treinamento.

- Uma sugestão é ao final do treinamento salvar o modelo treinado.

### 🎲 Conjunto de dados (dataset) 🎲

- Conforme explicado no trabalho, utilizou-se um dataset sintético para o treinamento, formado a partir da concatenação de outros dois. A escolha das imagens de cada classe (sem, correta e incorreta) se deu de forma pseudo-aleatória, e esse sorteio pode ser observado em ```dataset/montagem_particoes.ipynb``` , perceba que foi utilizado a estrutura de pastas existentes nos datasets originais. Além disso, cada nova execução irá gerar um conjunto de pastas sorteadas diferentes. O código mencionado sorteia as pastas (e por consequência as imagens que a compõem). o arquivo ```dataset/1_montagem_particoes_p1.pdf``` traz o resultado para o sorteio. 

- O conunto de dados para o teste foi baseado em imagens reais, a seleção buscou não inserir imagens iguais ou similares (rotações...).
- Na pasta dataset, pode-se obter o nome das imagens utilizadas tanto no conjunto de treinamento, como no de teste. Dessa forma, basta ir nos datasets originais, e baixá-las.  
