# Estudos Visão Computacional com Python
[![Twitter: marcelxsilva](https://img.shields.io/twitter/follow/marcelxsilva.svg?style=social)](https://twitter.com/marcelxsilva)

> # Sistemas de cores

Ja conhecemos o RGB e sabemos que no openCV essa ordem é invertida, colocando o azul em primeiro e o vermelho por ultimo BGR.

Uma imagem colorida é composta por três tipos de cores seguindo o padrão RGB, que tambem podem ser chamados de canais. Podemos visualizar esses canais individualmente.

```Python
import cv2
import numpy as np

img = cv2.imread('imagem.jpg')
(azul , verde, vermelho ) = cv2.split(img)

cv2.imshow('vermelho', vermelho)
cv2.imshow('verde', verde)
cv2.imshow('azul', azul)
cv2.waitKey(0)

```

A função split fará o trabalho pesado, separando os canais e assim podemos exibilos em diferentes tons.

Rode o código e verá o resultado.


É possivel modificar individualmente as numpy arrays, e depois junta-las para recriar a imagem.

```Python
import numpy as np
import cv2
img = cv2.imread('imagem.jpg')
(azul, verde, Vermelho) = cv2.split(img)
zeros = np.zeros(img.shape[:2], dtype = "uint8")
cv2.imshow("Vermelho", cv2.merge([zeros, zeros,
Vermelho]))
cv2.imshow("Verde", cv2.merge([zeros, verde, zeros]))
cv2.imshow("Azul", cv2.merge([azul, zeros, zeros]))
cv2.imshow("Original", img)
cv2.waitKey(0)
```

Rode o código em sua maquina e verá o resultado, ele exibirá a mesma imagem porem em tonalidade azul, vermelho e verde.

***
[Voltar ao Inicio](../README.md)

 Author **Marcelo Silva**

* Twitter: [@marcelxsilva](https://twitter.com/marcelxsilva)
