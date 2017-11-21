---
title: "Birikmeli bağımlılıklar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f2fd356ae37eda8820e3a6e0e31a8cecde8d3929
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Hedefleri](../build/targets.md)