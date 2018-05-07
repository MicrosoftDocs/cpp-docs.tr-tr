---
title: Derleyici Uyarısı (düzey 1) C4325 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4325
dev_langs:
- C++
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 936433987f823ae7d5d22cfd075f188dd5d4b1e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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