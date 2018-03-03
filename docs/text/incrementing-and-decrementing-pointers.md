---
title: "İşaretçileri Artırma ve azaltma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e9eccf65f091c8c5c273f6a65cb7e81b0d386afa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="incrementing-and-decrementing-pointers"></a>İşaretçileri Artırma ve Azaltma
Aşağıdaki ipuçlarını kullanın:  
  
-   Noktası ön baytlar, baytlara değil. Sondaki bayt gösteren bir işaretçi sağlamak için genellikle güvenli değildir. Genellikle bir dize İleri yerine ters tarama daha güvenlidir.  
  
-   İşaretçi artırma/azaltma işlevleri ve tüm bir karakter üzerinden taşıma makroları vardır:  
  
    ```  
    sz1++;  
    ```  
  
     Olur:  
  
    ```  
    sz1 = _mbsinc( sz1 );  
    ```  
  
     `_mbsinc` Ve `_mbsdec` işlevleri doğru artırmak ve içinde azaltma `character` karakter boyutu bakılmaksızın birimleri.  
  
-   Azaltır için aşağıdaki gibi dize head gösteren bir işaretçi gerekir:  
  
    ```  
    sz2--;  
    ```  
  
     Olur:  
  
    ```  
    sz2 = _mbsdec( sz2Head, sz2 );  
    ```  
  
     Alternatif olarak, geçerli bir karakter dizesi içinde baş işaretçinizi olabilir şekilde:  
  
    ```  
    sz2Head < sz2  
    ```  
  
     Bilinen geçerli baytı gösteren bir işaretçi olması gerekir.  
  
-   Daha hızlı çağrılar için önceki karakteri gösteren bir işaretçi korumak isteyebilirsiniz `_mbsdec`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MBCS programlama ipuçları](../text/mbcs-programming-tips.md)   
 [Bayt Endeksleri](../text/byte-indices.md)