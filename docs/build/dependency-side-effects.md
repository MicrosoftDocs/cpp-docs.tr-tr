---
title: Bağımlılık yan etkileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7537e077a43318a487163d014b49d52cef66ce19
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [Hedefler](../build/targets.md)