---
title: "Birden çok hedef | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- makefiles, targets
- multiple targets in NMAKE
- targets, multiple in NMAKE
- NMAKE program, targets
ms.assetid: b609a179-0b9f-4b08-9930-998047588ae0
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c610b5a65dfc676d12d414754248ba74ebc4b81c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="multiple-targets"></a>Birden Çok Hedef
NMAKE içindeki tek bir bağımlılığı birden çok hedef her ayrı açıklama bloğunda belirtildi olarak değerlendirir.  
  
 Örneğin, bu...  
  
```Output  
bounce.exe leap.exe : jump.obj  
   echo Building...  
```  
  
 .. belirtiminde bu değerlendirilir:  
  
```Output  
bounce.exe : jump.obj  
   echo Building...  
leap.exe : jump.obj  
   echo Building...  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hedefleri](../build/targets.md)