---
title: "Kayan nokta türlerinden dönüşümler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- converting floating point
- floating-point conversion
ms.assetid: 96804c8e-fa3b-4742-9006-0082ed9e57f2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4a95596b2c9e7312d4581d1a4c641c2466420158
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="conversions-from-floating-point-types"></a>Kayan Nokta Türlerinden Dönüşümler
A **float** dönüştürülen değer bir **çift** veya `long double`, veya bir **çift** dönüştürülen bir `long double`, değerindeki herhangi bir değişiklik olduğunda. A **çift** dönüştürülen değer bir **float** değeri temsil edilir tam olarak, mümkün olduğunda. Değeri tam olarak gösterilemezse duyarlık kaybolmuş olabilir. Sonucun aralığının dışında olması durumunda tanımlanmamış bir davranıştır. Bkz: [Floating-Point sabitleri sınırlamaları](../c-language/limits-on-floating-point-constants.md) kayan nokta türleri aralığı için.  
  
 Kayan değeri ilk dönüştürerek bir tam sayı değerine dönüştürülür bir **uzun**, ardından gelen **uzun** belirli tam sayı değerine değeri. Kayan değeri ondalık kısmı dönüştürme atılır bir **uzun**. Sonuç hala içine sığmayacak kadar büyük olup olmadığını bir **uzun**, dönüştürme işleminin sonucu tanımlanmadı.  
  
 **Microsoft özel**  
  
 Dönüştürülürken bir **çift** veya `long double` kayan noktalı sayıdan küçük kayan noktalı sayı, kayan nokta değişkeninin değeri için bir underflow oluştuğunda sıfır kesildi. Taşma bir çalışma zamanı hatasına neden olur. Microsoft C Derleyici eşlemeleri Not `long double` yazmak için **çift**.  
  
 **SON Microsoft özel**  
  
 Aşağıdaki tablo türleri kayan gelen dönüşümleri özetler.  
  
### <a name="conversions-from-floating-point-types"></a>Kayan Nokta Türlerinden Dönüşümler  
  
|Başlangıç|Bitiş|Yöntem|  
|----------|--------|------------|  
|**float**|`char`|Dönüştür **uzun**; Dönüştür **uzun** için`char`|  
|**float**|**short**|Dönüştür **uzun**; Dönüştür **uzun** için **kısa**|  
|**float**|**long**|Ondalık noktada keser. Sonuç olarak gösterilemeyecek kadar büyük olursa **uzun**, sonuç tanımlanmadı.|  
|**float**|**İmzasız short**|Dönüştür **uzun**; Dönüştür **uzun** için `unsigned` **kısa**|  
|**float**|`unsigned long`|Dönüştür **uzun**; Dönüştür **uzun** için `unsigned` **uzun**|  
|**float**|**double**|İç gösterimi değiştirme|  
|**float**|`long double`|İç gösterimi değiştirme|  
|**double**|`char`|Dönüştür **float**; Dönüştür **float** için`char`|  
|**double**|**short**|Dönüştür **float**; Dönüştür **float** için **kısa**|  
|**double**|**long**|Ondalık noktada keser. Sonuç olarak gösterilemeyecek kadar büyük olursa **uzun**, sonuç tanımlanmadı.|  
|**double**|**İmzasız short**|Dönüştür **uzun**; Dönüştür **uzun** için **kısa imzalanmamış**|  
|**double**|`unsigned long`|Dönüştür **uzun**; Dönüştür **uzun** için `unsigned` **uzun**|  
|**double**|**float**|Olarak temsil eden bir **float**. Varsa **çift** değeri temsil edilemez tam olarak **float**, duyarlık kaybına oluşur. Değer olarak gösterilemeyecek kadar büyük olursa **float**, sonuç tanımlanmadı.|  
|`long double`|`char`|Dönüştür **float**; Dönüştür **float** için`char`|  
|`long double`|**short**|Dönüştür **float**; Dönüştür **float** için **kısa**|  
|`long double`|**long**|Ondalık noktada keser. Sonuç olarak gösterilemeyecek kadar büyük olursa **uzun**, sonuç tanımlanmadı.|  
|`long double`|**İmzasız short**|Dönüştür **uzun**; Dönüştür **uzun** için `unsigned` **kısa**|  
|`long double`|`unsigned long`|Dönüştür **uzun**; Dönüştür **uzun** için `unsigned` **uzun**|  
|`long double`|**float**|Olarak temsil eden bir **float**. Varsa **çift** değeri temsil edilemez tam olarak **float**, duyarlık kaybına oluşur. Değer olarak gösterilemeyecek kadar büyük olursa **float**, sonuç tanımlanmadı.|  
|`long double`|**double**|**Uzun çift** değeri olarak değerlendirilir **çift**.|  
  
 Gelen dönüşümleri **float**, **çift**, veya `long double` değerler `unsigned long` dönüştürülen değerin en büyük pozitif büyükse doğru olmayan **uzun**değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama Dönüştürmeleri](../c-language/assignment-conversions.md)