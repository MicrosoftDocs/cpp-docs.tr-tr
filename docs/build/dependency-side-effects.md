---
title: "Bağımlılık yan etkileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9d19426a34620cfdd14b426b94757715ca2d1cbd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dependency-side-effects"></a>Bağımlılık Yan Etkileri
Bir hedef farklı konumlarda iki bağımlılık satırlardaki iki nokta (:) ile belirtilirse ve komut satırları yalnızca biri sonra görünüyorsa NMAKE bağımlılıkları bitişik veya birleştirilmiş gibi yorumlar. Çıkarım kuralı, hiçbir komut var, ancak bunun yerine bağımlılıklar için bir açıklama blok ait ve bir bağımlılık içeren belirtilen komutları yürütür varsayar bağımlılığı çağrılmaz. Örneğin, bu kuralları ayarlayın:  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
```  
  
 şunun gibi değerlendirilir:  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 Bu etkiyi çift iki nokta üst üste gerçekleşmez (`::`) kullanılır. Örneğin, bu kuralları ayarlayın:  
  
```Output  
bounce.exe :: jump.obj  
   echo Building bounce.exe...  
  
bounce.exe :: up.obj  
```  
  
 şunun gibi değerlendirilir:  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
# invokes an inference rule  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hedefleri](../build/targets.md)