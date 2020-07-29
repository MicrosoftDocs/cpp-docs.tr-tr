---
title: İmzalı tam sayı türlerinden dönüştürmeler
ms.date: 10/02/2019
helpviewer_keywords:
- integral conversions, from signed
- integers, converting
- conversions [C++], integral
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
ms.assetid: 5eea32f8-8b14-413d-acac-c063b3d118d7
ms.openlocfilehash: d41d2fd205a87f9f2be2179ffd8e38256a96e4f7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226483"
---
# <a name="conversions-from-signed-integral-types"></a>İmzalı tam sayı türlerinden dönüştürmeler

İşaretli bir tamsayı bir tamsayıya veya kayan nokta türüne dönüştürüldüğünde, özgün değer sonuç türünde gösterilebilir ise, değer değiştirilmez.

İşaretli bir tamsayı daha büyük bir tamsayıya dönüştürüldüğünde, değer, işaret genişletilir. Daha küçük boyutlu bir tamsayıya dönüştürüldüğünde, yüksek sıralı bitler kesilir. Sonuç, bu örnekte gösterildiği gibi sonuç türü kullanılarak yorumlanır:

```C
int i = -3;
unsigned short u;

u = i;
printf_s( "%hu\n", u );  // Prints 65533
```

İşaretli bir tamsayı bir kayan nokta türüne dönüştürülürken, özgün değer tam olarak sonuç türünde gösterilemeyen şekilde yoksa, sonuç bir sonraki daha yüksek veya daha düşük gösterilemeyen değerdir.

İntegral ve kayan nokta türlerinin boyutları hakkında daha fazla bilgi için bkz. [temel türlerin depolanması](../c-language/storage-of-basic-types.md).

Aşağıdaki tabloda, imzalanmış integral türlerinden dönüşümler özetlenmektedir. **`char`** Türün varsayılan olarak imzalandığını varsayar. Tür için varsayılan ayarı işaretsiz olarak değiştirmek için bir derleme zamanı seçeneği kullanırsanız **`char`** , bu tablodaki dönüşümler yerine, tür için [işaretsiz integral türleri tablosundan dönüştürmelerde](../c-language/conversions-from-unsigned-integral-types.md) verilen dönüştürmeler **`unsigned char`** .

**Microsoft'a Özgü**

, Microsoft derleyicisinde **`int`** farklıdır, **`long`** ancak eşdeğer türlerdir. **`int`** Bir değerin dönüştürülmesi, bir öğesinin dönüştürülmesine benzer şekilde devam eder **`long`** .

**SON Microsoft 'a özgü**

## <a name="table-of-conversions-from-signed-integral-types"></a>İşaretli integral türlerinden dönüştürme tablosu

|Kaynak|Amaç|Yöntem|
|----------|--------|------------|
|**`char`**<sup>1</sup>|**`short`**|Oturum uzat|
|**`char`**|**`long`**|Oturum uzat|
|**`char`**|**`long long`**|Oturum uzat|
|**`char`**|**`unsigned char`**|Stili koru; yüksek sıralı bit, işaret biti olarak işlevi kaybeder|
|**`char`**|**`unsigned short`**|İmza-uzat **`short`** ; Dönüştür **`short`****`unsigned short`**|
|**`char`**|**`unsigned long`**|İmza-uzat **`long`** ; Dönüştür **`long`****`unsigned long`**|
|**`char`**|**`unsigned long long`**|İmza-uzat **`long long`** ; Dönüştür **`long long`****`unsigned long long`**|
|**`char`**|**`float`**|İmza-uzat **`long`** ; Dönüştür **`long`****`float`**|
|**`char`**|**`double`**|İmza-uzat **`long`** ; Dönüştür **`long`****`double`**|
|**`char`**|**`long double`**|İmza-uzat **`long`** ; Dönüştür **`long`****`double`**|
|**`short`**|**`char`**|Düşük sıra baytını koru|
|**`short`**|**`long`**|Oturum uzat|
|**`short`**|**`long long`**|Oturum uzat|
|**`short`**|**`unsigned char`**|Düşük sıra baytını koru|
|**`short`**|**`unsigned short`**|Bit modelini koru; yüksek sıralı bit, işaret biti olarak işlevi kaybeder|
|**`short`**|**`unsigned long`**|İmza-uzat **`long`** ; Dönüştür **`long`****`unsigned long`**|
|**`short`**|**`unsigned long long`**|İmza-uzat **`long long`** ; Dönüştür **`long long`****`unsigned long long`**|
|**`short`**|**`float`**|İmza-uzat **`long`** ; Dönüştür **`long`****`float`**|
|**`short`**|**`double`**|İmza-uzat **`long`** ; Dönüştür **`long`****`double`**|
|**`short`**|**`long double`**|İmza-uzat **`long`** ; Dönüştür **`long`****`double`**|
|**`long`**|**`char`**|Düşük sıra baytını koru|
|**`long`**|**`short`**|Düşük sıralı kelimeyi koru|
|**`long`**|**`long long`**|Oturum uzat|
|**`long`**|**`unsigned char`**|Düşük sıra baytını koru|
|**`long`**|**`unsigned short`**|Düşük sıralı kelimeyi koru|
|**`long`**|**`unsigned long`**|Bit modelini koru; yüksek sıralı bit, işaret biti olarak işlevi kaybeder|
|**`long`**|**`unsigned long long`**|İmza-uzat **`long long`** ; Dönüştür **`long long`****`unsigned long long`**|
|**`long`**|**`float`**|As olarak temsil edin **`float`** . **`long`** Tam olarak gösterilemeyen bazı duyarlık kaybolur.|
|**`long`**|**`double`**|As olarak temsil edin **`double`** . **`long`** Tam olarak olarak temsil edileyemeyeceği **`double`** bazı duyarlık kaybolur.|
|**`long`**|**`long double`**|As olarak temsil edin **`double`** . **`long`** Tam olarak olarak temsil edileyemeyeceği **`double`** bazı duyarlık kaybolur.|
|**`long long`**|**`char`**|Düşük sıra baytını koru|
|**`long long`**|**`short`**|Düşük sıralı kelimeyi koru|
|**`long long`**|**`long`**|Düşük sıralı DWORD 'yi koru|
|**`long long`**|**`unsigned char`**|Düşük sıra baytını koru|
|**`long long`**|**`unsigned short`**|Düşük sıralı kelimeyi koru|
|**`long long`**|**`unsigned long`**|Düşük sıralı DWORD 'yi koru|
|**`long long`**|**`unsigned long long`**|Bit modelini koru; yüksek sıralı bit, işaret biti olarak işlevi kaybeder|
|**`long long`**|**`float`**|As olarak temsil edin **`float`** . **`long long`** Tam olarak gösterilemeyen bazı duyarlık kaybolur.|
|**`long long`**|**`double`**|As olarak temsil edin **`double`** . **`long long`** Tam olarak olarak temsil edileyemeyeceği **`double`** bazı duyarlık kaybolur.|
|**`long long`**|**`long double`**|As olarak temsil edin **`double`** . **`long long`** Tam olarak olarak temsil edileyemeyeceği **`double`** bazı duyarlık kaybolur.|

<sup>1</sup> tüm **`char`** girişler **`char`** türün varsayılan olarak imzalandığını varsayar.

## <a name="see-also"></a>Ayrıca bkz.

[Atama dönüştürmeleri](../c-language/assignment-conversions.md)
