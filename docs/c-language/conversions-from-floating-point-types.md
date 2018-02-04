---
title: "Kayan nokta türlerinden dönüşümler | Microsoft Docs"
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
- converting floating point
- floating-point conversion
ms.assetid: 96804c8e-fa3b-4742-9006-0082ed9e57f2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80e84ba9a78f78fd93d7bd7fedbcbfaf168a7ec2
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="conversions-from-floating-point-types"></a>Kayan nokta türlerinden dönüşümler

A **float** dönüştürülen değer bir **çift** veya **uzun çift**, veya bir **çift** dönüştürülen bir **uzunçift**, değerindeki herhangi bir değişiklik olduğunda. A **çift** dönüştürülen değer bir **float** değeri temsil edilir tam olarak, mümkün olduğunda. Değeri tam olarak gösterilemezse duyarlık kaybolmuş olabilir. Sonucun aralığının dışında olması durumunda tanımlanmamış bir davranıştır. Bkz: [Floating-Point sabitleri sınırlamaları](../c-language/limits-on-floating-point-constants.md) kayan nokta türleri aralığı için.

Kayan değeri ilk dönüştürerek bir tam sayı değerine dönüştürülür bir **uzun**, ardından gelen **uzun** belirli tam sayı değerine değeri. Kayan değeri ondalık kısmı dönüştürme atılır bir **uzun**. Sonuç hala içine sığmayacak kadar büyük olup olmadığını bir **uzun**, dönüştürme işleminin sonucu tanımlanmadı.

**Microsoft Specific**

Dönüştürülürken bir **çift** veya **uzun çift** kayan noktalı sayıdan küçük kayan noktalı sayı, kayan nokta değişkeninin değeri için bir underflow oluştuğunda sıfır kesildi. Taşma bir çalışma zamanı hatasına neden olur. Microsoft C Derleyici eşlemeleri Not **uzun çift** yazmak için **çift**.

**SON Microsoft özel**

Aşağıdaki tablo türleri kayan gelen dönüşümleri özetler.

## <a name="conversions-from-floating-point-types"></a>Kayan nokta türlerinden dönüşümler

|Başlangıç|Bitiş|Yöntem|
|----------|--------|------------|
|**float**|**char**|Dönüştür **uzun**; Dönüştür **uzun** için **char**|
|**float**|**short**|Dönüştür **uzun**; Dönüştür **uzun** için **kısa**|
|**float**|**long**|Ondalık noktada keser. Sonuç olarak gösterilemeyecek kadar büyük olursa **uzun**, sonuç tanımlanmadı.|
|**float**|**İmzasız short**|Dönüştür **uzun**; Dönüştür **uzun** için **kısa imzalanmamış**|
|**float**|**İmzasız long**|Dönüştür **uzun**; Dönüştür **uzun** için **uzun imzalanmamış**|
|**float**|**double**|İç gösterimi değiştirme|
|**float**|**uzun çift**|İç gösterimi değiştirme|
|**double**|**char**|Dönüştür **float**; Dönüştür **float** için **char**|
|**double**|**short**|Dönüştür **float**; Dönüştür **float** için **kısa**|
|**double**|**long**|Ondalık noktada keser. Sonuç olarak gösterilemeyecek kadar büyük olursa **uzun**, sonuç tanımlanmadı.|
|**double**|**İmzasız short**|Dönüştür **uzun**; Dönüştür **uzun** için **kısa imzalanmamış**|
|**double**|**İmzasız long**|Dönüştür **uzun**; Dönüştür **uzun** için **uzun imzalanmamış**|
|**double**|**float**|Olarak temsil eden bir **float**. Varsa **çift** değeri temsil edilemez tam olarak **float**, duyarlık kaybına oluşur. Değer olarak gösterilemeyecek kadar büyük olursa **float**, sonuç tanımlanmadı.|
|**uzun çift**|**char**|Dönüştür **float**; Dönüştür **float** için **char**|
|**uzun çift**|**short**|Dönüştür **float**; Dönüştür **float** için **kısa**|
|**uzun çift**|**long**|Ondalık noktada keser. Sonuç olarak gösterilemeyecek kadar büyük olursa **uzun**, sonuç tanımlanmadı.|
|**uzun çift**|**İmzasız short**|Dönüştür **uzun**; Dönüştür **uzun** için **kısa imzalanmamış**|
|**uzun çift**|**İmzasız long**|Dönüştür **uzun**; Dönüştür **uzun** için **uzun imzalanmamış**|
|**uzun çift**|**float**|Olarak temsil eden bir **float**. Varsa **çift** değeri temsil edilemez tam olarak **float**, duyarlık kaybına oluşur. Değer olarak gösterilemeyecek kadar büyük olursa **float**, sonuç tanımlanmadı.|
|**uzun çift**|**double**|**Uzun çift** değeri olarak değerlendirilir **çift**.|

Gelen dönüşümleri **float**, **çift**, veya **uzun çift** değerler **uzun imzasız** dönüştürülen değer ise doğru değil en büyük pozitif büyük **uzun** değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Atama Dönüştürmeleri](../c-language/assignment-conversions.md)  
