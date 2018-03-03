---
title: "Derleyici Uyarısı (düzey 1) C4325 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4325
dev_langs:
- C++
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab31150efc02601d7392470198e162e979ac4917
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4325"></a>Derleyici Uyarısı (düzey 1) C4325
**Standart bölümü için öznitelikler '**   
 ***bölüm* ' yoksayıldı**  
  
 Standart bir bölüm özniteliklerini değiştiremeyebilir. Örneğin:  
  
```  
#pragma section(".sdata", long)  
```  
  
 Bu üzerine `.sdata` kullanan standart bölüm **kısa** veri türü ile **uzun** veri türü.  
  
 Öznitelikleri değil değişebilir standart bölümler, kapsar.  
  
-   .Data  
  
-   .sdata  
  
-   .BSS  
  
-   .sbss  
  
-   .Text  
  
-   .const  
  
-   .sconst  
  
-   .rdata  
  
-   .srdata  
  
 Daha sonra ek bölümler eklenebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [section](../../preprocessor/section.md)