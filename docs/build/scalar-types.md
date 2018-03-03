---
title: "Skaler türler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 15b0915637025e176ee98d01be3991b30b4e6544
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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