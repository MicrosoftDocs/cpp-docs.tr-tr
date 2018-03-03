---
title: "Birden çok hedef | Microsoft Docs"
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
helpviewer_keywords:
- makefiles, targets
- multiple targets in NMAKE
- targets, multiple in NMAKE
- NMAKE program, targets
ms.assetid: b609a179-0b9f-4b08-9930-998047588ae0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a70a265318914b70928dce5fae2f486e63c16f0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Hedefler](../build/targets.md)