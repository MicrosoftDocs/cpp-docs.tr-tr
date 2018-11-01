---
title: Kayan Nokta Türlerinden Dönüşümler
ms.date: 01/29/2018
helpviewer_keywords:
- converting floating point
- floating-point conversion
ms.assetid: 96804c8e-fa3b-4742-9006-0082ed9e57f2
ms.openlocfilehash: 87e1554897326039649829539443795cbc0fabab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570563"
---
# <a name="conversions-from-floating-point-types"></a>Kayan nokta türlerinden dönüşümler

A **float** dönüştürülen değer bir **çift** veya **uzun çift**, veya bir **çift** dönüştürülen bir **uzunçift**, değişmez değer uygulanır. A **çift** dönüştürülen değer bir **float** değeri temsil tam olarak, mümkünse. Duyarlık değeri tam olarak temsil edilemiyorsa kaybolabilir. Sonucu aralık dışında ise tanımsız bir davranıştır. Bkz: [Floating-Point sabitleri sınırlamaları](../c-language/limits-on-floating-point-constants.md) aralığı kayan nokta türleri için.

Bir kayan değer ilk dönüştürerek bir tam sayı değerine dönüştürülür bir **uzun**, ardından gelen **uzun** değeri belirli bir tamsayı değeri. Kayan değer ondalık kısmını dönüştürme atılır bir **uzun**. Sonucu hala içine sığmayacak kadar büyük olup olmadığını bir **uzun**, dönüştürmenin sonucu tanımsızdır.

**Microsoft'a özgü**

Dönüştürülürken bir **çift** veya **uzun çift** yetersiz geldiğinde, kayan noktalı sayı daha küçük kayan noktalı sayı, kayan nokta değişkeninin değeri sıfıra yakınsayarak kısaltılır. Taşma bir çalışma zamanı hatasına neden olur. Microsoft C derleyicisi eşleyen Not **uzun çift** türüne **çift**.

**END Microsoft özgü**

Gelen kayan türlerden dönüştürmeler aşağıdaki tabloda özetlenmiştir.

## <a name="conversions-from-floating-point-types"></a>Kayan nokta türlerinden dönüşümler

|Başlangıç|Bitiş|Yöntem|
|----------|--------|------------|
|**float**|**char**|Dönüştürme **uzun**; dönüştürme **uzun** için **char**|
|**float**|**short**|Dönüştürme **uzun**; dönüştürme **uzun** için **kısa**|
|**float**|**long**|Ondalık noktası olacak şekilde kısaltın. Sonuç olarak gösterilemeyecek kadar çok büyük ise **uzun**, sonuç tanımsızdır.|
|**float**|**İmzasız short**|Dönüştürme **uzun**; dönüştürme **uzun** için **işaretsiz**|
|**float**|**İmzasız long**|Dönüştürme **uzun**; dönüştürme **uzun** için **işaretsiz uzun**|
|**float**|**double**|Değişiklik iç gösterimi|
|**float**|**uzun çift**|Değişiklik iç gösterimi|
|**double**|**char**|Dönüştürme **float**; dönüştürme **float** için **char**|
|**double**|**short**|Dönüştürme **float**; dönüştürme **float** için **kısa**|
|**double**|**long**|Ondalık noktası olacak şekilde kısaltın. Sonuç olarak gösterilemeyecek kadar çok büyük ise **uzun**, sonuç tanımsızdır.|
|**double**|**İmzasız short**|Dönüştürme **uzun**; dönüştürme **uzun** için **işaretsiz**|
|**double**|**İmzasız long**|Dönüştürme **uzun**; dönüştürme **uzun** için **işaretsiz uzun**|
|**double**|**float**|Olarak temsil eden bir **float**. Varsa **çift** değeri, tam olarak gösterilemez **float**, kesinlik kaybı oluşur. Değer olarak gösterilemeyecek kadar çok büyük ise **float**, sonuç tanımsızdır.|
|**uzun çift**|**char**|Dönüştürme **float**; dönüştürme **float** için **char**|
|**uzun çift**|**short**|Dönüştürme **float**; dönüştürme **float** için **kısa**|
|**uzun çift**|**long**|Ondalık noktası olacak şekilde kısaltın. Sonuç olarak gösterilemeyecek kadar çok büyük ise **uzun**, sonuç tanımsızdır.|
|**uzun çift**|**İmzasız short**|Dönüştürme **uzun**; dönüştürme **uzun** için **işaretsiz**|
|**uzun çift**|**İmzasız long**|Dönüştürme **uzun**; dönüştürme **uzun** için **işaretsiz uzun**|
|**uzun çift**|**float**|Olarak temsil eden bir **float**. Varsa **çift** değeri, tam olarak gösterilemez **float**, kesinlik kaybı oluşur. Değer olarak gösterilemeyecek kadar çok büyük ise **float**, sonuç tanımsızdır.|
|**uzun çift**|**double**|**Uzun çift** değer olarak kabul edildiği **çift**.|

Dönüştürmelere **float**, **çift**, veya **uzun çift** değerler **işaretsiz uzun** dönüştürülen değer ise doğru değil en fazla pozitif büyük **uzun** değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Atama Dönüştürmeleri](../c-language/assignment-conversions.md)
