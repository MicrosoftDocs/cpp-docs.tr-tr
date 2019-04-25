---
title: İmzasız Tam Sayı Türlerinden Dönüştürmeler
ms.date: 03/27/2019
helpviewer_keywords:
- integers, converting
- type casts, involving integers
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
- integral conversions, from unsigned
ms.assetid: 60fb7e10-bff9-4a13-8a48-e19f25a36a02
ms.openlocfilehash: 3f6136a721f84332451184baa648ebc7c909d5d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62312446"
---
# <a name="conversions-from-unsigned-integral-types"></a>İmzasız Tam Sayı Türlerinden Dönüştürmeler

İşaretsiz bir tamsayı ile daha kısa bir işaretsiz veya imzalı tamsayı yüksek sıra bitleri kesilmesi veya bir artık imzalanmamış veya imzalı tamsayı-sıfır genişleterek dönüştürülür. Daha fazla bilgi için [işaretsiz tam sayı türleri tablosu Dönüşümlerse](#conversions-from-unsigned-integral-types-table).

Yeni türü içinde gösterilebilir, değerin tam sayı türü ile işaretli bir tamsayıya daha küçük boyutlu indirgenir veya işaretsiz bir tamsayı, karşılık gelen bir işaretli tamsayıya dönüştürülen değer değiştirilmez. Ancak, değişiklikleri temsil ettiği imza biti ayarlanmışsa, aşağıdaki örnekte olduğu gibi değeri.

```C
int j;
unsigned short k = 65533;

j = k;
printf_s( "%hd\n", j );   // Prints -3
```

Temsil edilemeyen, sonucu uygulama tarafından tanımlanır. Bkz: [tür atama dönüştürmeleri](../c-language/type-cast-conversions.md) tam sayıların indirgenmesi'nın Microsoft C Derleyici işleme hakkında bilgi için. Aynı davranış sonuçları tamsayı dönüşümü veya tür tamsayı atama.

İmzasız değerler değerlerine korur ve doğrudan C'de gösterilebilir değil bir şekilde dönüştürülür Bir dönüştürmedir tek özel durum **işaretsiz uzun** için **float**, hangi kaybeder en düşük sıra bitleri. Aksi takdirde, değeri, işaretli veya işaretsiz korunur. İntegral türünde bir değer kayan dönüştürülür ve değer gösterilebilir aralığının dışında olduğunda sonuç tanımsızdır. (Bkz [temel türlerin depolanması](../c-language/storage-of-basic-types.md) integral ve kayan nokta türleri için aralığı hakkında bilgi için.)

İmzasız tam sayı türlerinden dönüştürmeler aşağıdaki tabloda özetlenmiştir.

## <a name="conversions-from-unsigned-integral-types-table"></a>İmzasız tam sayı türleri tablosu dönüşümlerse

|Başlangıç|Bitiş|Yöntem|
|----------|--------|------------|
|**İmzasız char**|**char**|Bit deseni korumak; yüksek sıralı bitten imza haline gelir.|
|**İmzasız char**|**short**|Sıfır uzatma|
|**İmzasız char**|**long**|Sıfır uzatma|
|**İmzasız char**|**İmzasız short**|Sıfır uzatma|
|**İmzasız char**|**İmzasız long**|Sıfır uzatma|
|**İmzasız char**|**float**|Dönüştürme **uzun**; dönüştürme **uzun** için **float**|
|**İmzasız char**|**double**|Dönüştürme **uzun**; dönüştürme **uzun** için **çift**|
|**İmzasız char**|**uzun çift**|Dönüştürme **uzun**; dönüştürme **uzun** için **çift**|
|**İmzasız short**|**char**|Düşük düzey baytı korur|
|**İmzasız short**|**short**|Bit deseni korumak; yüksek sıralı bitten imza haline gelir.|
|**İmzasız short**|**long**|Sıfır uzatma|
|**İmzasız short**|**İmzasız char**|Düşük düzey baytı korur|
|**İmzasız short**|**İmzasız long**|Sıfır uzatma|
|**İmzasız short**|**float**|Dönüştürme **uzun**; dönüştürme **uzun** için **float**|
|**İmzasız short**|**double**|Dönüştürme **uzun**; dönüştürme **uzun** için **çift**|
|**İmzasız short**|**uzun çift**|Dönüştürme **uzun**; dönüştürme **uzun** için **çift**|
|**İmzasız long**|**char**|Düşük düzey baytı korur|
|**İmzasız long**|**short**|Düşük düzey word koru|
|**İmzasız long**|**long**|Bit deseni korumak; yüksek sıralı bitten imza haline gelir.|
|**İmzasız long**|**İmzasız char**|Düşük düzey baytı korur|
|**İmzasız long**|**İmzasız short**|Düşük düzey word koru|
|**İmzasız long**|**float**|Dönüştürme **uzun**; dönüştürme **uzun** için **float**|
|**İmzasız long**|**double**|Doğrudan dönüştürme **çift**|
|**İmzasız long**|**uzun çift**|Dönüştürme **uzun**; dönüştürme **uzun** için **çift**|

**Microsoft'a özgü**

Microsoft C derleyicisi için **işaretsiz int** türüdür eşdeğer **işaretsiz uzun** türü. Dönüştürme bir **işaretsiz int** değeri geçer dönüştürülmesi aynı şekilde bir **işaretsiz uzun**. Dönüştürmelere **işaretsiz uzun** değerler **float** dönüştürülen değer en fazla pozitif imzalı büyükse doğru olmadığını **uzun** değeri.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Atama Dönüştürmeleri](../c-language/assignment-conversions.md)
