---
title: Skaler türler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5490bb33cafd8d2942e434ab9c50e34441506463
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381177"
---
# <a name="scalar-types"></a>Ölçekli Türler
Veri erişimi herhangi hizalamasını kaynaklanabilir rağmen veri performans kaybı (veya bunların bir birden çok) önlemek için kendi doğal sınırında hizalanacak önerilir. Numaralandırmalar sabit tamsayı olan ve 32 bit tamsayı olarak kabul edilir. Aşağıdaki hizalama değerlerini kullanarak hizalama ilgili olarak aşağıdaki tabloda önerilen depolama alanını ve tür tanımı için açıklanmaktadır:  
  
-   Bayt - 8 bit  
  
-   Word - 16 bit  
  
-   Çift Word - 32 bit  
  
-   Dört Word - 64 bit  
  
-   Octa Word - 128 bit  
  
|||||  
|-|-|-|-|  
|Skaler tür|C veri türü|Depolama boyutu (bayt)|Önerilen hizalama|  
|**INT8**|`char`|1.|Bayt|  
|**UINT8**|`unsigned char`|1.|Bayt|  
|**INT16**|**short**|2|Word|  
|**UINT16**|**İmzasız short**|2|Word|  
|**INT32**|**int, uzun**|4|Doubleword|  
|**UINT32**|**İmzasız int, Long imzalanmamış**|4|Doubleword|  
|**INT64**|`__int64`|8|Quadword|  
|**UINT64**|**İmzasız __int64**|8|Quadword|  
|**FP32 (tek duyarlık)**|**float**|4|Doubleword|  
|**FP64 (çift duyarlık)**|**double**|8|Quadword|  
|**İŞARETÇİ**|**\***|8|Quadword|  
|`__m64`|**Yapı __m64**|8|Quadword|  
|`__m128`|**Yapı __m128**|16|Octaword|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Türler ve Depolama](../build/types-and-storage.md)