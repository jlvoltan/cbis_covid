# cbis_covid  😷


📌 Trata-se de repositório para os códigos utilizados no trabalho "Identificação automática do uso de máscaras de proteção facial: um estudo comparativo".
O trabalho foi apresentado no XIX Congresso Brasileiro de Informática em Saúde (CBIS - 2022).


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

