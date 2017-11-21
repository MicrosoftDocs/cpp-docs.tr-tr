---
title: "Bellek üzerine yazmalar için denetimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4560fb580d3d1b24feccf84dc07bde7dc38458c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="checking-for-memory-overwrites"></a>Bellek Üzerine Yazmalarını Denetleme
Öbek işleme işlevi çağrısında bir erişim ihlali alırsanız programınızı yığın bozulmuş mümkündür. Bu durumun yaygın bir belirti olacaktır:  
  
```  
Access Violation in _searchseg  
```  
  
 [_Heapchk](../../c-runtime-library/reference/heapchk.md) işlevi hem hata ayıklama modunda kullanılabilir ve yayın derlemeleri (yalnızca Windows NT) çalışma zamanı kitaplığı yığın bütünlüğünü doğrulamak için. Kullanabileceğiniz `_heapchk` kadar aynı şekilde `AfxCheckMemory` işlevi bir öbek üzerine yazma, örneğin yalıtmak için:  
  
```  
if(_heapchk()!=_HEAPOK)  
   DebugBreak();  
```  
  
 Bu işlev arızalanırsa, ayırmak, bu noktada yığın bozulmuş gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yayın derlemesi sorunlarını giderme](../../build/reference/fixing-release-build-problems.md)