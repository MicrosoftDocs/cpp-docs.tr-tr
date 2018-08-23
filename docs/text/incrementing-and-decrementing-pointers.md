---
title: İşaretçileri Artırma ve azaltma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4fff5d7ec20ce052e4d831f1556432186ebc7bb
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603366"
---
# <a name="incrementing-and-decrementing-pointers"></a>İşaretçileri Artırma ve Azaltma
Aşağıdaki ipuçlarını kullanın:  
  
-   İşaret baytlara değil, ön baytlar. Sondaki baytı işaretçiniz güvenli değil. Genellikle ileri yerine ters bir dizesini tara daha güvenlidir.  
  
-   İşaretçi artırma/azaltma işlevleri ve tam bir karakter üzerinden taşınan makroları vardır:  
  
    ```  
    sz1++;  
    ```  
  
     olur:  
  
    ```  
    sz1 = _mbsinc( sz1 );  
    ```  
  
     `_mbsinc` Ve `_mbsdec` işlevleri doğru bir şekilde artırın ve içinde azaltma `character` birimi, karakter boyutundan bağımsız olarak.  
  
-   Azaltır için bir işaretçi olduğu aşağıdaki gibi dize karşılaştırması gerekir:  
  
    ```  
    sz2--;  
    ```  
  
     olur:  
  
    ```  
    sz2 = _mbsdec( sz2Head, sz2 );  
    ```  
  
     Alternatif olarak, geçerli bir karakter dizesi, baş işaretçinizi olabilir gibi:  
  
    ```  
    sz2Head < sz2  
    ```  
  
     Bilinen geçerli baytı için bir işaretçi olması gerekir.  
  
-   Daha hızlı çağrılar için önceki karaktere bir işaretçi korumak isteyebileceğiniz `_mbsdec`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MBCS programlama ipuçları](../text/mbcs-programming-tips.md)   
 [Bayt Endeksleri](../text/byte-indices.md)