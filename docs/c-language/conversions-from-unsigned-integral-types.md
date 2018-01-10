---
title: "İmzasız tam sayı türlerinden dönüştürmeler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- integers, converting
- type casts, involving integers
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
- integral conversions, from unsigned
ms.assetid: 60fb7e10-bff9-4a13-8a48-e19f25a36a02
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6c2ecc7c4a0308a1a7d182cc0bdaf04c2ed6b6e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="conversions-from-unsigned-integral-types"></a>İmzasız Tam Sayı Türlerinden Dönüştürmeler
İşaretsiz tamsayıya yüksek düzey BITS kesilmesiyle tarafından daha kısa bir veya imzalanmış tamsayı veya sıfır genişletme tarafından artık veya imzalanmış tamsayı dönüştürülür (bkz [imzasız tam sayı türlerinden dönüştürmeler](#_clang_table_4..3) tablo).  
  
 Yeni türünü temsil edilebilir, daha küçük boyutu ile imzalanmış bir tamsayı değeri Tamsayı türünde indirgenir veya işaretsiz tamsayıya karşılık gelen kendi imzalı tamsayıya dönüştürülür değeri değişmeden olur. Ancak, değişiklikleri temsil ettiği oturum biti ayarlanmışsa aşağıdaki örnekteki değer.  
  
```  
int j;  
unsigned short k = 65533;  
  
j = k;  
printf_s( "%hd\n", j );   // Prints -3  
```  
  
 Temsil edilemez, uygulama tanımlı sonucudur. Bkz: [tür atama dönüşümleri](../c-language/type-cast-conversions.md) indirgenmesi Microsoft C derleyicinin işleme hakkında bilgi için. Aynı davranışı sonuçları tamsayı dönüştürmesi veya tür tamsayı atama.  
  
 İmzasız değerler değerlerine korur ve doğrudan c dilinde gösterilebilir değil şekilde dönüştürülür Dönüştürme tek istisnası `unsigned long` için **float**, hangi kaybederse en düşük düzey BITS. Aksi halde değer, imzalanmış veya imzalanmamış korunur. Tamsayı türünde bir değer kayan dönüştürülür ve değer gösterilebilir aralığın dışında olduğunda sonuç tanımlanmamıştır. (Bkz [temel türleri depolama](../c-language/storage-of-basic-types.md) ayrılmaz ve kayan nokta türleri için izin verilen aralığın hakkında bilgi için.)  
  
 İmzasız tam sayı türlerinden dönüştürmeler aşağıdaki tabloda özetlenmiştir.  
  
### <a name="conversions-from-unsigned-integral-types"></a>İmzasız Tam Sayı Türlerinden Dönüştürmeler  
  
|Başlangıç|Bitiş|Yöntem|  
|----------|--------|------------|  
|`unsigned char`|`char`|Bit desenini korumak; yüksek sıralı bit bit oturum olur|  
|`unsigned char`|**short**|Sıfır genişletme|  
|`unsigned char`|**long**|Sıfır genişletme|  
|`unsigned char`|**İmzasız short**|Sıfır genişletme|  
|`unsigned char`|`unsigned long`|Sıfır genişletme|  
|`unsigned char`|**float**|Dönüştür **uzun**; Dönüştür **uzun** için **float**|  
|`unsigned char`|**double**|Dönüştür **uzun**; Dönüştür **uzun** için **çift**|  
|`unsigned char`|`long double`|Dönüştür **uzun**; Dönüştür **uzun** için **çift**|  
|**İmzasız short**|`char`|Düşük düzey baytı korur|  
|**İmzasız short**|**short**|Bit desenini korumak; yüksek sıralı bit bit oturum olur|  
|**İmzasız short**|**long**|Sıfır genişletme|  
|**İmzasız short**|`unsigned char`|Düşük düzey baytı korur|  
|**İmzasız short**|`unsigned long`|Sıfır genişletme|  
|**İmzasız short**|**float**|Dönüştür **uzun**; Dönüştür **uzun** için **float**|  
|**İmzasız short**|**double**|Dönüştür **uzun**; Dönüştür **uzun** için **çift**|  
|**İmzasız short**|`long double`|Dönüştür **uzun**; Dönüştür **uzun** için **çift**|  
|`unsigned long`|`char`|Düşük düzey baytı korur|  
|`unsigned long`|**short**|Düşük düzey word koru|  
|`unsigned long`|**long**|Bit desenini korumak; yüksek sıralı bit bit oturum olur|  
|`unsigned long`|`unsigned char`|Düşük düzey baytı korur|  
|`unsigned long`|**İmzasız short**|Düşük düzey word koru|  
|`unsigned long`|**float**|Dönüştür **uzun**; Dönüştür **uzun** için **float**|  
|`unsigned long`|**double**|Doğrudan Dönüştür **çift**|  
|`unsigned long`|`long double`|Dönüştür **uzun**; Dönüştür **uzun** için **çift**|  
  
 **Microsoft özel**  
  
 Microsoft 32-bit C derleyicisi için `unsigned int` türüdür eşdeğer `unsigned long` türü. Dönüştürme bir `unsigned int` değeri geçer dönüştürülmesi aynı şekilde bir `unsigned long`. Gelen dönüşümleri `unsigned long` değerler **float** dönüştürülen değerin imzalı en büyük pozitif büyükse doğru olmayan **uzun** değeri.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama Dönüştürmeleri](../c-language/assignment-conversions.md)