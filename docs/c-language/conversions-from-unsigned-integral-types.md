---
title: İmzasız tam sayı türlerinden dönüştürmeler
ms.date: 10/02/2019
helpviewer_keywords:
- integers, converting
- type casts, involving integers
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
- integral conversions, from unsigned
ms.assetid: 60fb7e10-bff9-4a13-8a48-e19f25a36a02
ms.openlocfilehash: 08b88b1343f56f8d79fc39c53505b26caecfe3c4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226470"
---
# <a name="conversions-from-unsigned-integral-types"></a>İmzasız tam sayı türlerinden dönüştürmeler

İşaretsiz bir tamsayı bir tamsayı veya kayan nokta türüne dönüştürüldüğünde, sonuç türünde orijinal değer gösterilebilir ise değer değiştirilmez.

İşaretsiz bir tamsayıyı daha büyük boyutlu bir tamsayıya dönüştürürken değer sıfır genişletilir. Daha küçük boyutta bir tamsayıya dönüştürürken, yüksek sıralı bitler kesilir. Sonuç, bu örnekte gösterildiği gibi sonuç türü kullanılarak yorumlanır.

```C
unsigned k = 65533;
short j;

j = k;
printf_s( "%hd\n", j );   // Prints -3
```

İşaretsiz bir tamsayı bir kayan nokta türüne dönüştürülürken, özgün değer tam olarak sonuç türünde temsil edilene kadar, sonuç bir sonraki daha yüksek veya daha düşük gösterilemeyen değerdir.

İntegral ve kayan nokta türlerinin boyutları hakkında bilgi için bkz. [temel türlerin depolanması](../c-language/storage-of-basic-types.md) .

**Microsoft'a Özgü**

Microsoft derleyicisinde **`unsigned`** (veya **`unsigned int`** ) ve **`unsigned long`** farklı ancak eşdeğer türlerdir. Bir değerin dönüştürülmesi **`unsigned int`** , bir öğesinin dönüştürülmesine benzer şekilde devam eder **`unsigned long`** .

**SON Microsoft 'a özgü**

Aşağıdaki tabloda, imzasız integral türlerinden dönüşümler özetlenmektedir.

## <a name="table-of-conversions-from-unsigned-integral-types"></a>İşaretsiz integral türlerindeki dönüştürmelerin tablosu

|Kaynak|Amaç|Yöntem|
|----------|--------|------------|
|**`unsigned char`**|**`char`**|Bit modelini koru; yüksek sıralı bit, işaret biti olur|
|**`unsigned char`**|**`short`**|Sıfır-uzat|
|**`unsigned char`**|**`long`**|Sıfır-uzat|
|**`unsigned char`**|**`long long`**|Sıfır-uzat|
|**`unsigned char`**|**`unsigned short`**|Sıfır-uzat|
|**`unsigned char`**|**`unsigned long`**|Sıfır-uzat|
|**`unsigned char`**|**`unsigned long long`**|Sıfır-uzat|
|**`unsigned char`**|**`float`**|Dönüştür **`long`** ; Dönüştür **`long`****`float`**|
|**`unsigned char`**|**`double`**|Dönüştür **`long`** ; Dönüştür **`long`****`double`**|
|**`unsigned char`**|**`long double`**|Dönüştür **`long`** ; Dönüştür **`long`****`double`**|
|**`unsigned short`**|**`char`**|Düşük sıra baytını koru|
|**`unsigned short`**|**`short`**|Bit modelini koru; yüksek sıralı bit, işaret biti olur|
|**`unsigned short`**|**`long`**|Sıfır-uzat|
|**`unsigned short`**|**`long long`**|Sıfır-uzat|
|**`unsigned short`**|**`unsigned char`**|Düşük sıra baytını koru|
|**`unsigned short`**|**`unsigned long`**|Sıfır-uzat|
|**`unsigned short`**|**`unsigned long long`**|Sıfır-uzat|
|**`unsigned short`**|**`float`**|Dönüştür **`long`** ; Dönüştür **`long`****`float`**|
|**`unsigned short`**|**`double`**|Dönüştür **`long`** ; Dönüştür **`long`****`double`**|
|**`unsigned short`**|**`long double`**|Dönüştür **`long`** ; Dönüştür **`long`****`double`**|
|**`unsigned long`**|**`char`**|Düşük sıra baytını koru|
|**`unsigned long`**|**`short`**|Düşük sıralı kelimeyi koru|
|**`unsigned long`**|**`long`**|Bit modelini koru; yüksek sıralı bit, işaret biti olur|
|**`unsigned long`**|**`long long`**|Sıfır-uzat|
|**`unsigned long`**|**`unsigned char`**|Düşük sıra baytını koru|
|**`unsigned long`**|**`unsigned short`**|Düşük sıralı kelimeyi koru|
|**`unsigned long`**|**`unsigned long long`**|Sıfır-uzat|
|**`unsigned long`**|**`float`**|Dönüştür **`long`** ; Dönüştür **`long`****`float`**|
|**`unsigned long`**|**`double`**|Doğrudan Dönüştür**`double`**|
|**`unsigned long`**|**`long double`**|Dönüştür **`long`** ; Dönüştür **`long`****`double`**|
|**`unsigned long long`**|**`char`**|Düşük sıra baytını koru|
|**`unsigned long long`**|**`short`**|Düşük sıralı kelimeyi koru|
|**`unsigned long long`**|**`long`**|Düşük sıralı DWORD 'yi koru|
|**`unsigned long long`**|**`long long`**|Bit modelini koru; yüksek sıralı bit, işaret biti olur|
|**`unsigned long long`**|**`unsigned char`**|Düşük sıra baytını koru|
|**`unsigned long long`**|**`unsigned short`**|Düşük sıralı kelimeyi koru|
|**`unsigned long long`**|**`unsigned long`**|Düşük sıralı DWORD 'yi koru|
|**`unsigned long long`**|**`float`**|Dönüştür **`long`** ; Dönüştür **`long`****`float`**|
|**`unsigned long long`**|**`double`**|Doğrudan Dönüştür**`double`**|
|**`unsigned long long`**|**`long double`**|Dönüştür **`long`** ; Dönüştür **`long`****`double`**|

## <a name="see-also"></a>Ayrıca bkz.

[Atama dönüştürmeleri](../c-language/assignment-conversions.md)
