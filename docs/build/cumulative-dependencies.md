---
title: Birikmeli bağımlılıklar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d502912a8aeee2e6b3782e7795f44238386e1dba
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="cumulative-dependencies"></a>Birikmeli Bağımlılıklar
Bir hedef yineleniyorsa açıklama bloğunda toplu bağımlılıklardır.  
  
 Örneğin, bu kuralları ayarlamak,  
  
```Output  
bounce.exe : jump.obj  
bounce.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 şunun gibi değerlendirilir:  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 Birden çok hedef birden çok bağımlılık satırlarındaki tek açıklama bloğundaki her bir ayrı açıklama bloğu içinde belirtildi, ancak son bağımlılık satırına olmayan hedefleri komutları blok kullanmayın sanki değerlendirilir. NMAKE çıkarım kuralı gibi hedefler için kullanmayı dener.  
  
 Örneğin, bu kuralları ayarlamak,  
  
```Output  
leap.exe bounce.exe : jump.obj  
bounce.exe climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 şunun gibi değerlendirilir:  
  
```Output  
  
leap.exe : jump.obj  
# invokes an inference rule  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hedefler](../build/targets.md)