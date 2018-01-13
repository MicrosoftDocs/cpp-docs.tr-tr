---
title: "Toplamlar ve birleşimler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: aggregates [C++], and unions
ms.assetid: 859fc211-b111-4f12-af98-de78e48f9b92
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 74ee1bbcf1a39171b18c09274543c72e0b844748
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="aggregates-and-unions"></a>Toplamlar ve Birleşimler
Diziler, yapılar ve birleşimleri gibi diğer türleri tutarlı toplama ve birleşim depolama ve veri alma olun daha sıkı hizalama gereksinimleri vardır. Dizi, yapı ve birleşim tanımlarında şunlardır:  
  
 Dizi  
 Sıralı bir grup bitişik veri nesneleri içerir. Her nesne bir öğe adı verilir. Bir dizi içinde tüm öğeleri aynı boyut ve veri türüne sahip.  
  
 Yapı  
 Sıralı bir veri nesneleri grubunu içerir. Bir dizi öğelerinden farklı olarak, bir yapı içindeki veri nesneleri farklı veri türleri ve boyutlarına sahip olabilir. Her bir yapı veri nesnesinde bir üye adı verilir.  
  
 UNION  
 Adlandırılmış üyeler kümesinin herhangi birini tutan bir nesne. Adlandırılmış küme üyeleri herhangi bir türde olabilir. Bir birleşim için ayrılan depolama alanı, o UNION artı hizalama için gerekli herhangi bir doldurmaya en büyük üyesi için gerekli depolama alanına eşittir.  
  
 Aşağıdaki tabloda birleşimler ve yapıları skaler üyeleri için şiddetle önerilen hizalamasını gösterir.  
  
||||  
|-|-|-|  
|Skaler tür|C veri türü|Gerekli hizalama|  
|**INT8**|`char`|Bayt|  
|**UINT8**|`unsigned char`|Bayt|  
|**INT16**|**short**|Word|  
|**UINT16**|**İmzasız short**|Word|  
|**INT32**|**int, uzun**|Doubleword|  
|**UINT32**|**İmzasız int, Long imzalanmamış**|Doubleword|  
|**INT64**|`__int64`|Quadword|  
|**UINT64**|**İmzasız __int64**|Quadword|  
|**FP32 (tek duyarlık)**|**float**|Doubleword|  
|**FP64 (çift duyarlık)**|**double**|Quadword|  
|**İŞARETÇİ**|**\***|Quadword|  
|`__m64`|**Yapı __m64**|Quadword|  
|`__m128`|**Yapı __m128**|Octaword|  
  
 Aşağıdaki toplam hizalama kurallar geçerlidir:  
  
-   Bir dizi hizalamasını bir dizi öğelerin hizalamasını ile aynıdır.  
  
-   Bir yapının ya da bir UNION başlangıcını hizalamasını herhangi bir üyenin en fazla hizalamasını ' dir. Yapı veya birlik içindeki her üye, önceki üyeyi bağlı olarak örtülü dahili doldurmayı gerektirebilir önceki tabloda tanımlanan uygun kendi hizalama yerleştirilmelidir.  
  
-   Yapı boyutu son öğesinden sonra doldurma gerektirebilir kendi hizalama ayrılmaz bir katı olmalıdır. Yapılar ve birleşimleri dizilerde gruplandırılabilir olduğundan, her dizi öğesi, bir yapının veya birleşim başlar ve daha önceden belirlenen uygun hizalama son gerekir.  
  
-   Verileri önceki kurallar korunduğu sürece hizalama gereksinimlerinden daha büyük olacak şekilde hizalayın mümkündür.  
  
-   Bireysel bir derleyici paket boyutu nedeniyle yapısının ayarlayabilir. Örneğin [/Zp (yapı üyesi hizalama)](../build/reference/zp-struct-member-alignment.md) yapıları paketleme ayarlamak için sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Türler ve Depolama](../build/types-and-storage.md)