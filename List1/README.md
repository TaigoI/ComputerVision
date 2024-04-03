## Lista 1
Abaixo, os resultados das questões

### Item 1

Implemente uma funcao que receba uma imagem em formato PPM, o tamanho n de um filtro espacial com dimensões n*n e a matriz com os pesos do filtro, e aplique o filtro com uma convolução, gerando e salvando a imagem resultante no disco em formato PPM. Você não pode usar a OpenCV em nenhum desses passos. As especificações do formato PPM podem ser encontradas aqui: https://netpbm.sourceforge.net/doc/ppm.html

#### Resultados do Item 1
Para testar a filtragem, apliquei o kernel conhecido como "Emboss": 
```math
FILTER = \begin{bmatrix} 
-2 & -1 & 0 \\
-1 &  1 & 1 \\
 0 &  1 & 2
\end{bmatrix}
```

Os resultados foram salvos tanto em .ppm, como pede a questão, quanto em .jpg, para exibição neste README.

<div>
  <img src="https://github.com/TaigoI/ComputerVision/blob/main/List1/Item1/results/building_compare.jpg?raw=true" alt="Building" style="height: 15vw; width: 40vw;">
  <img src="https://github.com/TaigoI/ComputerVision/blob/main/List1/Item1/results/falls_compare.jpg?raw=true" alt="Falls" style="height: 15vw; width: 40vw;">
  <img src="https://github.com/TaigoI/ComputerVision/blob/main/List1/Item1/results/tree_compare.jpg?raw=true" alt="Tree" style="height: 15vw; width: 40vw;">
</div>

### Item 2

Usando a função da questão 1, pesquise um filtro passa-alta e aplique-o em 3 imagens distintas, variando o valor de n em 3 unidades em cada imagem. O que acontece quando n cresce?

#### Resultados do Item 2
Para testar a filtragem, apliquei o filtro n=3 "Sharpen" e versões adaptadas para n=6 e n=9:

```math
SHARPEN\_3 = \begin{bmatrix} 
 0 & -1 &  0 \\
-1 &  8 & -1 \\
 0 & -1 &  0 \\
\end{bmatrix}
/ 4
```

```math
SHARPEN\_6 = \begin{bmatrix} 
 0 & -1 & -2 & -2 & -1 &  0 \\
-1 & -2 & -4 & -4 & -2 & -1 \\
-2 & -4 & 18 & 18 & -4 & -2 \\
-2 & -4 & 18 & 18 & -4 & -2 \\
-1 & -2 & -4 & -4 & -2 & -1 \\
 0 & -1 & -2 & -2 & -1 &  0
\end{bmatrix}
/ 8
```

```math
SHARPEN\_9 = \begin{bmatrix} 
 0 & -1 &  -2 &  -4 &  -6 &  -4 &  -2 &  -1 &  0 \\
-1 & -2 &  -4 &  -6 &  -8 &  -6 &  -4 &  -2 & -1 \\
-2 & -4 &  -6 &  -8 & -10 &  -8 &  -6 &  -4 & -2 \\
-4 & -6 &  -8 & -10 &  46 & -10 &  -8 &  -6 & -4 \\
-6 & -8 & -10 &  46 & 204 &  46 & -10 &  -8 & -6 \\
-4 & -6 &  -8 & -10 &  46 & -10 &  -8 &  -6 & -4 \\
-2 & -4 &  -6 &  -8 & -10 &  -8 &  -6 &  -4 & -2 \\
-1 & -2 &  -4 &  -6 &  -8 &  -6 &  -4 &  -2 & -1 \\
 0 & -1 &  -2 &  -4 &  -6 &  -4 &  -2 &  -1 &  0
\end{bmatrix}
/ 20
```

Os filtros de passa-alta funcionam como filtros de aumento da nitidez (Sharpening); Também realçam o ruído na imagem.
Nas imagens abaixo, você verá, na ordem: Original, SHARPEN_3, SHARPEN_6, SHARPEN_9. Quanto maior o kernel do filtro, mais intenso é o efeito de aumento da nitidez, ao ponto que, no SHARPEN_9, o efeito está tão intenso que desfigura a imagem.

<div>
  <img src="https://github.com/TaigoI/ComputerVision/blob/main/List1/Item2/results/building_compare.jpg?raw=true" alt="Building" style="height: 7.5vw; width: 40vw;">
  <img src="https://github.com/TaigoI/ComputerVision/blob/main/List1/Item2/results/falls_compare.jpg?raw=true" alt="Falls" style="height: 7.5vw; width: 40vw;">
  <img src="https://github.com/TaigoI/ComputerVision/blob/main/List1/Item2/results/tree_compare.jpg?raw=true" alt="Tree" style="height: 7.5vw; width: 40vw;">
</div>

### Item 3

Usando a função da questão 1, pesquise um filtro passa-baixa e aplique-o em 3 imagens distintas, variando o valor de n em 3 unidades em cada imagem. O que acontece quando n cresce?

#### Resultados do Item 3
Para testar a filtragem, apliquei o filtro n=3 "Blur" e versões adaptadas para n=6 e n=9:

```math
BLUR\_3 = \begin{bmatrix} 
 1 & 1 & 1 \\
 1 & 1 & 1 \\
 1 & 1 & 1
\end{bmatrix}
/ 9
```

```math
BLUR\_6 = \begin{bmatrix} 
 1 & 1 & 1 & 1 & 1 & 1 \\
 1 & 1 & 1 & 1 & 1 & 1 \\
 1 & 1 & 1 & 1 & 1 & 1 \\
 1 & 1 & 1 & 1 & 1 & 1 \\
 1 & 1 & 1 & 1 & 1 & 1 \\
 1 & 1 & 1 & 1 & 1 & 1
\end{bmatrix}
/ 36
```

```math
$BLUR\_9 = \begin{bmatrix} 
 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 \\
 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 \\
 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 \\
 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 \\
 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 \\
 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 \\
 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 \\
 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 \\
 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1
\end{bmatrix}
/ 81
```

Os filtros de passa-alta funcionam como filtros de desfoque (Blurring), eles reduzem o ruído na imagem.
Nas imagens abaixo, você verá, na ordem: Original, BLUR_3, BLUR_6, BLUR_9. Quanto maior o kernel do filtro, mais intenso é o efeito de desfoque.

<div>
  <img src="https://github.com/TaigoI/ComputerVision/blob/main/List1/Item3/results/building_compare.jpg?raw=true" alt="Building" style="height: 7.5vw; width: 40vw;">
  <img src="https://github.com/TaigoI/ComputerVision/blob/main/List1/Item3/results/falls_compare.jpg?raw=true" alt="Falls" style="height: 7.5vw; width: 40vw;">
  <img src="https://github.com/TaigoI/ComputerVision/blob/main/List1/Item3/results/tree_compare.jpg?raw=true" alt="Tree" style="height: 7.5vw; width: 40vw;">
</div>

### Item 4

Um filtro passa-baixa bastante conhecido é o filtro Gaussiano. Através de uma máscara determinada por um desvio padrão σ, é possível fazer o que chamamos de suavização gaussiana de uma imagem. Considere o filtro 5x5 de desvio padrão unitário abaixo:

```math
g = \begin{bmatrix} 
1/273 &  4/273 &  7/273 &  4/273 &  1/273 \\
4/273 & 16/273 & 26/273 & 16/273 &  4/273 \\
7/273 & 26/273 & 41/273 & 26/273 &  7/273 \\
4/273 & 16/273 & 26/273 & 16/273 &  4/273 \\
1/273 &  4/273 &  7/273 &  4/273 &  1/273
\end{bmatrix}
```

Crie uma imagem I de dimensões 100 × 100 que contém um único valor não nulo localizado no centro da imagem.<br>Utilizando o filtro gaussiano acima, calcule e exiba I * g, onde ∗ é a notação para o operador de convolução.

#### Resultados do Item 4

<img src="https://github.com/TaigoI/ComputerVision/blob/main/List1/Item4/results/compare.jpg?raw=true" alt="Tree" style="height: 15vw; width: 40vw;">

### Item 5

Pesquise e implemente um filtro para remoção de ruídos que não possa ser representado com convoluções.

#### Resultados do Item 5

O método de denoise através de FFT transforma a imagem em uma representação no domínio da frequência, que através do shift e a aplicação de threshold, elimina do sinal as frequências mais altas (ruído). Por se tratar de uma transformação do sinal baseada em frequência, não pode ser representado por abordagem convolucional.

Abaixo, as imagens originais e em seguida as imagens depois de aplicar denoise por FFT.

<div>
  <img src="https://github.com/TaigoI/ComputerVision/blob/main/List1/Item5/results/original.jpg?raw=true" alt="Original" style="height: 7.5vw; width: 40vw;">
  <img src="https://github.com/TaigoI/ComputerVision/blob/main/List1/Item5/results/denoised.jpg?raw=true" alt="FTTed" style="height: 7.5vw; width: 40vw;">
</div>

