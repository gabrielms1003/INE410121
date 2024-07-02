**Disciplina:** INE410121 - Visão Computacional
**Professor:** Aldo Von Wangenheim
**Grupo:** João Paulo Bedretchuk, Victor Marques Araújo do Nascimento, Gabriel Martins de Souza
**PROJETO FINAL:** Detecção de Defeitos em Estradas

**INTRODUÇÃO**
A estrutura viária é essencial para o progresso econômico e social, garantindo deslocamentos seguros e eficazes que impactam a qualidade de vida. No entanto, a manutenção das vias enfrenta desafios como desgaste devido ao uso intenso e condições climáticas, além de restrições financeiras e humanas. A visão computacional oferece uma solução inovadora ao usar processamento de imagens e aprendizado automático para identificar falhas nas estradas, permitindo inspeções mais rápidas, precisas e econômicas. Isso melhora a segurança e a eficiência do transporte rodoviário, otimiza investimentos em manutenção e promove o desenvolvimento de veículos autônomos, beneficiando a sociedade como um todo.

**MÉTODO CLÁSSICO**
A implementação do algoritmo de detecção de defeitos em estradas, baseada em métodos clássicos, seguiu as seguintes etapas:
**Importação e pré-processamento dos dados:** realiza a leitura e pré-processamento das imagens e dos arquivos de anotação (formato Yolo).
**Janelamento e classificação:** as imagens são subdivididas em janelas de dimensões 80x80. Cada janela é classificada como contendo ou não buracos com base nas anotações.
**Otsu threshold:** as janelas são binarizadas utilizando o método de limiarização de Otsu.
**Extração de características (HoG):** utilizando HoG, as características das janelas são extraídas.
**Treinamento do classificador:** realiza o treinamento do classificador XGBoost com base nos conjuntos de dados gerados.
**Determinação da região do buraco:** realiza o treinamento do classificador XGBoost com base nos conjuntos de dados gerados.

**DEEP LEARNING**
A implementação do algoritmo de detecção de defeitos em estradas, baseada em deep learning, seguiu as seguintes etapas:
**Segmentação de Instâncias para Detecção Detalhada de Objetos:** O projeto utiliza o YOLOv8-seg para segmentação de instâncias, que fornece máscaras precisas, rótulos de classe e pontuações de confiança para cada objeto, essencial para tarefas detalhadas como a análise de danos em estradas.
**YOLOv8n-seg para Segmentação de Buracos em Tempo Real:** O modelo YOLOv8n-seg é escolhido pelo seu equilíbrio entre velocidade e precisão, tornando-o ideal para aplicações de segmentação em tempo real.
**Preparação do Conjunto de Dados:** Um conjunto de dados especializado de 780 imagens de buracos foi compilado, com 720 para treinamento e 60 para validação. As imagens são redimensionadas para 640x640 pixels e aumentadas com técnicas como inversão, corte e ajuste de brilho.
**Ajuste Fino do Modelo com Aprendizado por Transferência:** O modelo YOLOv8-seg é ajustado usando aprendizado por transferência para adaptá-lo à detecção e segmentação precisa de buracos, aproveitando o conjunto de dados especializado.
**Avaliação e Inferência:** O modelo passa por uma avaliação abrangente e inferência em imagens de validação e novos vídeos de teste para garantir precisão e confiabilidade em cenários reais.
**Avaliação de Danos em Estradas em Tempo Real:** O modelo final é implantado para análise de vídeo em tempo real para estimar continuamente a área de danos causados por buracos, apoiando estratégias de reparo de estradas e fornecendo alertas imediatos de perigo.

**LINKS**
Apresentação de slides - https://docs.google.com/presentation/d/1pxbjyKWmcD4ymmnkeOzPEk7jxBNAkkoLaelxGcZHab4/edit?usp=sharing
Vídeo - https://youtu.be/y402KjXZi8E
Código fonte - https://github.com/gabrielms1003/INE410121
Base de dados - https://github.com/michelpf/dataset-pothole?tab=readme-ov-file
