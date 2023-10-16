---
title: Lab Report | Illustrations on Image Encryption & Steganography
publishDate: 2023-10-13 17:18:00
img: /labs/lab1_dct/minia.png
img_alt: Steganography
description: |
 Course: Digital Content Protection
tags:
  - Steganography
  - Encryption
  - Lab Report
---
<style>
  pre{
    border-radius: 5px;
    margin: 0 2px;
    background-color: #f2f2f2;
  }
</style>

This report's aim is to test and evalutate different steganography and encryption methods on images. Indeed, some methods might not fit with images or with the needs of the user.

We will be using a Python (notebook) as well as the OpenCV library to manipulate images.

##### Loading data

Let's first load the image we will be using for this report.

```python
img = cv2.imread('./images/lenna.png', cv2.IMREAD_GRAYSCALE)
lenna = np.array(img)
```

We will be loading lenna.png as a gray-scale image and convert it to a numpy array for further manipulations.

--- 

#### CEASAR Cypher

The CEASAR cypher is a simple encryption method that shifts the letters of a message by a certain amount. For example, if we shift the letters of the alphabet by 3, A becomes D, B becomes E, C becomes F, etc.

Applied to images, this consists of shifting the pixels' value by a certain amount, on chosen channels (luminance or RGB for example).

##### Encryption & Decryption

Let's define the functions to encrypt and decrypt an image using the CEASAR cypher.

```python
def encode_ceasar(image, shift):
    encoded = np.zeros(image.shape)
    for i in range(image.shape[0]):
        for j in range(image.shape[1]):
            encoded[i][j] = (image[i][j] + shift) % 256
    return encoded

def decode_ceasar(image, shift):
    decoded = np.zeros(image.shape)
    for i in range(image.shape[0]):
        for j in range(image.shape[1]):
            decoded[i][j] = (image[i][j] - shift) % 256
    return decoded
```

**Results**


![CEASAR encryption of Lenna](/labs/lab1_dct/ceasar_lenna.png)

**Analysis**

*What do you notice ?*
- We notice that the decoded image isn't altered compared to the original. This is because the Ceasar cipher is a lossless encryption method.

*Which is the difference between the Ceasar cipher applied to text and to images ? Why ?*
- Firstly, the modulus that we apply to the alphabet is different. Indeed, for our image, we apply a modulus of 256 while for text, we'll apply a modulus of 26. This is because the size of the vocabulary is different (256 gray levels, 26 letters).
- As it offsets each pixel with the same value, the encoded image is still understandable wheras there is no perceptible pattern in encoded text.

Example for Baboon.png:

![CEASAR encryption of Baboon](/labs/lab1_dct/ceasar_baboon.png)

*What do you notice ?*

- We notice that the baboon is even more recognizable once encoded. This can maybe be attributed to the higher spatial density of the baboon texture.

Thus the Ceasar method is better used on images with **lower spatial density textures.**

---

#### Simple Substitution

The simple substitution method is a more complex encryption method that consists of replacing each letter of the alphabet by another one. For example, A becomes Z, B becomes Y, C becomes X, etc.

Applied to images, this consists of replacing each pixel's value by another one, on chosen channels (luminance or RGB for example).

To do so, we will use a lookup table that will map each pixel's value to another one.

##### Encryption & Decryption

Let's define the functions to encrypt and decrypt an image using the simple substitution method:

```python
def encode_ceasar_sub(image, shift):
    encoded = np.zeros(image.shape)
    for i in range(image.shape[0]):
        for j in range(image.shape[1]):
            encoded[i][j] = shift[image[i][j]]
    return encoded

def decode_ceasar_sub(image, shift):
    decoded = np.zeros(image.shape)
    pos = [x for x in range(256)]
    decipher = [x for x in range(256)]
    for i in range(256):
        decipher[shift[i]] = i
    for i in range(image.shape[0]):
        for j in range(image.shape[1]):
            decoded[i][j] = decipher[int(image[i][j])]
    return decoded
```

As we're only working with luminance value, a simple array can be used as a key.

```python
key = [x for x in range(256)]
shuffle(key)
```

**Results**

![Simple Substitution encryption of Lenna](/labs/lab1_dct/simple_sub_lenna.png)


![Simple Substitution encryption of Baboon](/labs/lab1_dct/simple_sub_baboon.png)

**Analysis**

As we can see, this encryption algorithm is more semantically destructive than the Ceasar cipher. Indeed, the encoded image is less recognizable but it still maintains some of the original image's features.
We also notice that high density textures are more noisy and less recognizable than homogeneous areas.

---

#### Simple Transpotition

The simple transposition method is a more complex encryption method that consists of swapping each letter of the alphabet with another one. For example, A becomes B, B becomes C, C becomes A, etc.

Applied to images, this consists of swapping each pixel's value with another one, on chosen channels (luminance or RGB for example).

![Simple Transposition Lenna](/labs/lab1_dct/simple_transpo_lenna.png)

![Simple Transposition Baboon](/labs/lab1_dct/simple_transpo_baboon.png)
###### from Andrea Miens & Marilou Grignoli's report

**Analysis**

As we can see, this encryption algorithm is semantically destructive, as once encoded, only noise is left. This is because the algorithm swaps each pixel's value with another one, thus destroying the image's structure. This is a very effective encryption algorithm for images.

---

#### Least Significant Bit

The LSB method is a steganography method that consists of replacing the least significant bit of each pixel's value with a bit of the message to hide.

Applied to images, this consists of replacing the least significant bit of each pixel's value with a bit of the message to hide, on chosen channels (luminance or RGB for example).

##### Encryption & Decryption

Let's define the functions to encrypt and decrypt an image using the LSB method:

```python
def encode_lsb(image):
    lsb = np.zeros(image.shape)
    for i in range(image.shape[0]):
        for j in range(image.shape[1]):
            if (i < 256 and j < 256) or  (i > 256 and j > 256):
                lsb[i][j] = image[i][j] - image[i][j] % 2
            else:
                lsb[i][j] = image[i][j] - (image[i][j] % 2 +1)
    return lsb

def decode_lsb(image):
    key = np.zeros(image.shape)
    for i in range(image.shape[0]):
        for j in range(image.shape[1]):
            key[i][j] = image[i][j] % 2
    return key
```

The encryption function will replace the least significant bit of each pixel's value as follows:
-if the pixel is in the upper left or lower right quadrant, the LSB will be replaced by a 0 (thus making it even)
-if the pixel is in the upper right or lower left quadrant, the LSB will be replaced by a 1 (thus making it odd)

**Results**

![LSB encryption of Lenna](/labs/lab1_dct/LSB_lenna.png)

**Analysis**

This algorithm allowed us to hide a checker pattern in the original image without it being noticeable when not deciphered.

---

#### LSB | Resilience against JPEG Compression

This steps consists of testing the resilience of the LSB method against JPEG compression.

**Results**

![LSB encryption of Lenna](/labs/lab1_dct/LSB_JPEG_lenna.png)

**Analysis**

As we can see, the LSB method is not very resilient against JPEG compression. Indeed, the checker pattern fades away at a compression rate of 75%.

#### LSB | Resilience against PNG Compression

This steps consists of testing the resilience of the LSB method against PNG compression.

**Results**

![LSB encryption of Lenna](/labs/lab1_dct/LSB_PNG_lenna.png)

**Analysis**

As we can see, the LSB method is very resilient against PNG compression. This is explained by the lossless caracteristic of PNG compression.

---

#### 2 Least Significant Bits

The 2 LSB method is a steganography method that consists of replacing the 2 least significant bits of each pixel's value with 2 bits of the message to hide.

**Encryption & Decryption**

Let's define the functions to encrypt and decrypt an image using the 2 LSB method:

```python
def encode_lsb_2(image):
    lsb = np.zeros(image.shape)
    for i in range(image.shape[0]):
        for j in range(image.shape[1]):
            if (i <= 256 and  j <= 256): #UpperLeft
                lsb[i][j] = image[i][j] - image[i][j] % 4
            elif (i > 256 and j <= 256): # Upper Right
                lsb[i][j] = image[i][j] - (image[i][j] % 4) + 2
            elif (i <= 256 and j > 256): #Lower Left
                lsb[i][j] = image[i][j] - (image[i][j] % 4) + 1
            elif (j > 256 and i > 256):#Down Right
                lsb[i][j] = image[i][j] - (image[i][j] % 4) + 3

    return lsb

def decode_lsb_2(image):
    key = np.zeros(image.shape)
    for i in range(image.shape[0]):
        for j in range(image.shape[1]):
            key[i][j] = image[i][j] % 4
    return key
```

The encryption algorithm insert 4 differents values in the image, depending on the pixel's position:
- Upper left: 00 (0)
- Upper right: 01 (1)
- Lower left: 10 (2)
- Lower right: 11 (3)

**Results**

![2 LSB encryption of Lenna](/labs/lab1_dct/2LSB_lenna.png)

**Analysis**

This algorithm allowed us to hide a checker pattern in the original image without it being noticeable when not deciphered. 

---

#### 2 LSB | Resilience against JPEG Compression

This steps consists of testing the resilience of the 2 LSB method against JPEG compression.

**Results**

![2 LSB encryption of Lenna](/labs/lab1_dct/2LSB_lenna_JPEG.png)

**Analysis**

As we can see, the 2 LSB method is not very resilient either against JPEG compression. Indeed, the checker pattern fades away at a compression rate of 75%.

---

### Conclusion

In this report, we tested and evaluated different steganography and encryption methods on images. We noticed that some methods are more resilient than others against compression. We also noticed that some methods are more semantically destructive than others.

To summarize, we saw that:
- The Ceasar cipher is a lossless encryption method that is better used on images with lower spatial density textures.
- The substitution cipher is a lossy encryption method that is better used on images with higher spatial density textures.
- The transposition cipher is a lossy encryption method that is very effective for images.
- The LSB method is a steganography method that is not very resilient against JPEG compression but very resilient against PNG compression.
- The 2 LSB method is a steganography method that is not very resilient against JPEG compression either.




