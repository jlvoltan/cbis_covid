# cbis_covid  😷


📌 Trata-se de repositório para os códigos utilizados no trabalho "Identificação automática do uso de máscaras de proteção facial: um estudo comparativo".
O trabalho foi apresentado no XIX Congresso Brasileiro de Informática em Saúde (CBIS - 2022).

✏️  Maiores explicações sobre a metodologia utilizada podem ser obtidas no referido artigo.

### 🎓 Como citar🎓 

```
@article{Voltan_Goldschmidt_Oliva_Duarte_Casanova_Teixeira_2023, place={Brasil},
title={Identificação automática do uso de máscaras de proteção facial: um estudo comparativo},
volume={15}, 
url={https://jhi.sbis.org.br/index.php/jhi-sbis/article/view/1077}, 
DOI={10.59681/2175-4411.v15.iEspecial.2023.1077}, 
abstractNote={"Objetivo: O uso de máscaras de proteção é uma importante medida para diminuir a transmissão da COVID-19 e de outras doenças. O presente trabalho teve como objetivo realizar um estudo comparativo entre diferentes modelos de aprendizado profundo aplicados na identificação da máscara de proteção (pessoa sem máscara, com máscara ou com máscara incorretamente posicionada). Métodos: foram implementados e avaliados os modelos de Redes Neurais Convolucionais MobileNetV3, Xception, VGG19. Foi utilizada a técnica de transferência de aprendizado na implementação e ajuste desses modelos. Resultados: Os modelos avaliados apresentaram acurácias que variaram entre 42% e 86%, esta última obtida pelo modelo Xception, superando os resultados reportados na literatura correlata. Conclusão: Os resultados apontam para o potencial promissor do modelo Xception que, ao viabilizar o monitoramento automático, permite a orientação de pessoas quanto ao correto uso de máscaras de proteção, dessa forma, contribuindo para diminuir o espalhamento de doenças através das vias aéreas.}, 
number={Especial},
 journal={Journal of Health Informatics},
 author={Voltan, José and Goldschmidt, Ronaldo and Oliva, Jefferson and Duarte, Julio and Casanova, Dalcimar and Teixeira, Marcelo},
 year={2023}, 
month={jul.} }

```

_Obs.: Outros fornmatos de citação podem ser encontrados em https://jhi.sbis.org.br/index.php/jhi-sbis/article/view/1077_


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

### 🤖 Modelos 🤖

- Os códigos dos modelos são identificados como ```modelo-xxx-n.ipynb``` onde _xxx_ representa a arquitetura utilizada e _n_ representa a abordagem. Por sua vez, ```modelo_yyy_m.ipynb``` representam os modelos da arquitetura simples, em que yyy pode ser a arqwuitetura A, B, C ou D, e o m relembra alguns detalhes dessa arquitetura (normalização, ou escala cinza). 
