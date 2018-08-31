---
title: Toplamlar ve birleşimler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- aggregates [C++], and unions
ms.assetid: 859fc211-b111-4f12-af98-de78e48f9b92
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a22fae86c48a0dcbfb43c0de79a44195945aa25a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223117"
---
# <a name="aggregates-and-unions"></a>Toplamlar ve Birleşimler
Diziler, yapılar ve birleşimler, diğer türleri, tutarlı toplama ve birleşim depolama ve veri alımı sağlayan daha sıkı hizalama gereksinimleri vardır. Dizi, yapı ve birleşim tanımlarında şunlardır:  
  
 Dizi  
 Bir sıralı bitişik veri nesnelerini içerir. Her nesne bir öğe adı verilir. Bir dizi içindeki tüm öğeleri aynı boyuta ve veri türüne sahip.  
  
 Yapı  
 Bir sıralanmış veri nesneleri içerir. Bir dizi öğelerinden farklı olarak, bir yapı içinde veri nesneleri farklı veri türleri ve boyutları olabilir. Her bir yapı veri nesnesinde bir üye adı verilir.  
  
 UNION  
 Herhangi bir adlandırılmış üyelerin kümesini tutan nesne. Adlandırılmış kümesi üyeleri herhangi bir türde olabilir. Bir birleşimin ayrılan depolama alanı, en büyük hizalama için gerekli tüm doldurma yanı sıra bu birleşim üyesi için gerekli olan depolama eşittir.  
  
 Aşağıdaki tablo, skaler üyelerinin birleşimleri ve yapıları için kesin önerilen hizalama gösterir.  
  
||||  
|-|-|-|  
|Skalar türü|C veri türü|Gerekli hizalama|  
|**INT8**|**char**|Bayt|  
|**UINT8**|**İmzasız char**|Bayt|  
|**INT16**|**short**|Word|  
|**UINT16**|**İmzasız short**|Word|  
|**INT32**|**int**, **uzun**|Doubleword|  
|**UINT32**|**işaretsiz int, işaretsiz uzun**|Doubleword|  
|**INT64**|**__int64**|Quadword|  
|**UINT64**|**imzalanmamış __int64**|Quadword|  
|**FP32 (tek duyarlık)**|**float**|Doubleword|  
|**FP64 (çift duyarlık)**|**double**|Quadword|  
|**İŞARETÇİ**|<strong>\*</strong>|Quadword|  
|**__m64**|**Yapı __m64**|Quadword|  
|**__m128**|**Yapı __m128**|Octaword|  
  
 Aşağıdaki toplama hizalama kurallar geçerlidir:  
  
-   Bir dizinin hizalama, bir dizinin öğelerin hizalamasını ile aynıdır.  
  
-   Herhangi bir üyenin en büyük hizalama başına bir yapı veya bir birleşim hizalamadır. Yapı veya birleşim içerisindeki her üye uygun hizalamanın önceki üye bağlı olarak örtük iç doldurma gerektirebilir önceki tabloda tanımlandığı gibi yerleştirilmelidir.  
  
-   Yapı boyutu doldurma son üyesinden sonra gerektirebilir, hizalama, tümleşik bir katı olmalıdır. Yapılar ve birleşimler dizilerde gruplandırılabilir olduğundan, yapı veya birleşim her dizi öğesi başlayıp bitmelidir önceden belirlenen uygun hizalaması.  
  
-   Verileri önceki kurallar korunduğu sürece hizalama gereksinimlerinden daha büyük olacak şekilde hizalayın mümkündür.  
  
-   Ayrı bir derleyici paketleme boyutu nedeniyle bir yapının ayarlayabilirsiniz. Örneğin [/Zp (yapı üyesi hizalama)](../build/reference/zp-struct-member-alignment.md) yapıları paketleme ayarlamak için sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Türler ve Depolama](../build/types-and-storage.md)
