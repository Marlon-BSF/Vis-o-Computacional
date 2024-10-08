## Visao-Computacional
Utilização de tratamento de imagem para identificar contornos.

# Conversão para escala de cinza e binarização

Converte a imagem RGB para escala de cinza (img_gray).
Armazena o valor máximo de intensidade de pixel na imagem em escala de cinza.
cv2.threshold: aplica uma limiarização à imagem. Aqui, THRESH_BINARY_INV inverte a imagem, transformando os pixels acima de um certo limiar em preto (0) e os abaixo em branco (255).

# Morfologia
Cria um kernel de morfologia de 5x5, preenchido com uns.
cv2.morphologyEx: aplica uma operação de abertura, que remove pequenas regiões de ruído na imagem binária.

# Filtragem por desfoque (blurring)
Aplica um desfoque à imagem em escala de cinza usando um filtro de média com um kernel de 5x5, suavizando a imagem e reduzindo ruídos.

# Detecção de bordas com Canny
cv2.Canny: detecta bordas na imagem. É aplicada duas vezes: uma vez na imagem em escala de cinza e outra na imagem desfocada, usando o mesmo limiar.

# Encontrar e desenhar contornos
cv2.findContours: encontra contornos na imagem binária. Os contornos são armazenados em uma lista e classificados por área.
cv2.drawContours: desenha os contornos encontrados na cópia da imagem original, utilizando a cor vermelha.
