# ICTS_Desafio_PDI

HDCP é a sigla para “High-bandwidth Digital Content Protection” e trata-se de um protocolo implementado nos dispositivos HDMI e DVI para impedir a transmissão de dados sem a devida autorização dos proprietários legais.

- Resumindo, é um sistema antipirataria para conteúdos digitais. 


- O gerador de sinal HDMI produz uma imagem em color bar e um OSD (On-screen display) que contém os status do HDCP e do EDID (Extended Display Identification Data) podendo ser OK e/ou NG (No Good) como mostrado na imagem abaixo:

![Exemplo](../imagens/2.jpg)

### 1. Escreva um algoritmo em Python que identifique os textos presente em uma imagem fornecida como entrada e gere como saída uma tupla que informe se a palavra OK se encontra ou não na imagem.

- Observe atentamente que as imagens estão com os textos de cabeça para baixo, pois a aquisição da imagem se faz com o display virado de cabeça para baixo, e que a solução precisa identificar os textos e exibi-los na saída.


- Há a possibilidade de ter imagens que não apresentem nenhum texto devido a falha de comunicação com o gerador de sinal, nesse caso a saída deve informar que a palavra OK não foi encontrada.


- Atente-se a um código limpo, organizado, documentado e com ideias claras da solução proposta.

### 2. Solução:

- A solução implementada fez uso de técnicas de Visão Computacional e Inteligência Artificial para determinar o status das imagens.


    - Transformações foram aplicadas à imagem para eliminar informações irrelevantes e localizar os textos na mesma;
    - Determinada a ROI, foi possível utilizar a ferramenta Tesseract de reconhecimento de caracteres para determinar o que estava escrito e localizar os OKs;
    - Determinada a posição dos OKs a determinação dos status HDCP e EDID se torna trivial;
    
# Observações:

- A detecção não é infalível, de modo que imagens com baixa qualidade levam a falhas na detecção do OK pela máscara criada ou na detecção do texto pelo OCR.
    - Nessas situações o rótulo NG (Not Good) é atribuído ao status correspondente;
