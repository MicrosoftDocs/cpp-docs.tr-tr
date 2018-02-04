---
title: "İmzasız tam sayı türlerinden dönüştürmeler | Microsoft Docs"
ms.custom: 
ms.date: 01/29/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- integers, converting
- type casts, involving integers
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
- integral conversions, from unsigned
ms.assetid: 60fb7e10-bff9-4a13-8a48-e19f25a36a02
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c00afa6ee5f084365663ca6c1e11c569b4e6be0
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="conversions-from-unsigned-integral-types"></a>İmzasız Tam Sayı Türlerinden Dönüştürmeler

İşaretsiz tamsayıya yüksek düzey BITS kesilmesiyle tarafından daha kısa bir veya imzalanmış tamsayı veya sıfır genişletme tarafından artık veya imzalanmış tamsayı dönüştürülür (bkz [imzasız tam sayı türlerinden dönüştürmeler](#_clang_table_4..3) tablo).

Yeni türünü temsil edilebilir, daha küçük boyutu ile imzalanmış bir tamsayı değeri Tamsayı türünde indirgenir veya işaretsiz tamsayıya karşılık gelen kendi imzalı tamsayıya dönüştürülür değeri değişmeden olur. Ancak, değişiklikleri temsil ettiği oturum biti ayarlanmışsa aşağıdaki örnekteki değer.

```C
int j;
unsigned short k = 65533;

j = k;
printf_s( "%hd\n", j );   // Prints -3
```

Temsil edilemez, uygulama tanımlı sonucudur. Bkz: [tür atama dönüşümleri](../c-language/type-cast-conversions.md) indirgenmesi Microsoft C derleyicinin işleme hakkında bilgi için. Aynı davranışı sonuçları tamsayı dönüştürmesi veya tür tamsayı atama.

İmzasız değerler değerlerine korur ve doğrudan c dilinde gösterilebilir değil şekilde dönüştürülür Dönüştürme tek istisnası **uzun imzasız** için **float**, hangi kaybederse en düşük düzey BITS. Aksi halde değer, imzalanmış veya imzalanmamış korunur. Tamsayı türünde bir değer kayan dönüştürülür ve değer gösterilebilir aralığın dışında olduğunda sonuç tanımlanmamıştır. (Bkz [temel türleri depolama](../c-language/storage-of-basic-types.md) ayrılmaz ve kayan nokta türleri için izin verilen aralığın hakkında bilgi için.)

İmzasız tam sayı türlerinden dönüştürmeler aşağıdaki tabloda özetlenmiştir.

## <a name="conversions-from-unsigned-integral-types"></a>İmzasız tam sayı türlerinden dönüştürmeler

|Başlangıç|Bitiş|Yöntem|
|----------|--------|------------|
|**İmzasız char**|**char**|Bit desenini korumak; yüksek sıralı bit bit oturum olur|
|**İmzasız char**|**short**|Sıfır genişletme|
|**İmzasız char**|**long**|Sıfır genişletme|
|**İmzasız char**|**İmzasız short**|Sıfır genişletme|
|**İmzasız char**|**İmzasız long**|Sıfır genişletme|
|**İmzasız char**|**float**|Dönüştür **uzun**; Dönüştür **uzun** için **float**|
|**İmzasız char**|**double**|Dönüştür **uzun**; Dönüştür **uzun** için **çift**|
|**İmzasız char**|**uzun çift**|Dönüştür **uzun**; Dönüştür **uzun** için **çift**|
|**İmzasız short**|**char**|Düşük düzey baytı korur|
|**İmzasız short**|**short**|Bit desenini korumak; yüksek sıralı bit bit oturum olur|
|**İmzasız short**|**long**|Sıfır genişletme|
|**İmzasız short**|**İmzasız char**|Düşük düzey baytı korur|
|**İmzasız short**|**İmzasız long**|Sıfır genişletme|
|**İmzasız short**|**float**|Dönüştür **uzun**; Dönüştür **uzun** için **float**|
|**İmzasız short**|**double**|Dönüştür **uzun**; Dönüştür **uzun** için **çift**|
|**İmzasız short**|**uzun çift**|Dönüştür **uzun**; Dönüştür **uzun** için **çift**|
|**İmzasız long**|**char**|Düşük düzey baytı korur|
|**İmzasız long**|**short**|Düşük düzey word koru|
|**İmzasız long**|**long**|Bit desenini korumak; yüksek sıralı bit bit oturum olur|
|**İmzasız long**|**İmzasız char**|Düşük düzey baytı korur|
|**İmzasız long**|**İmzasız short**|Düşük düzey word koru|
|**İmzasız long**|**float**|Dönüştür **uzun**; Dönüştür **uzun** için **float**|
|**İmzasız long**|**double**|Doğrudan Dönüştür **çift**|
|**İmzasız long**|**uzun çift**|Dönüştür **uzun**; Dönüştür **uzun** için **çift**|

**Microsoft Specific**

Microsoft C derleyicisi için **imzasız int** türüdür eşdeğer **uzun imzasız** türü. Dönüştürme bir **imzasız int** değeri geçer dönüştürülmesi aynı şekilde bir **uzun imzasız**. Gelen dönüşümleri **uzun imzasız** değerler **float** dönüştürülen değerin imzalı en büyük pozitif büyükse doğru olmayan **uzun** değeri.

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca bkz.

[Atama Dönüştürmeleri](../c-language/assignment-conversions.md)  
