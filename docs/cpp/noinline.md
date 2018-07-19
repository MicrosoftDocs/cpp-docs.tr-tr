---
title: noinline | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noinline_cpp
dev_langs:
- C++
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37098e904402a42f6ff28e594db265fc07b4d458
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948137"
---
# <a name="noinline"></a>noinline
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 **__declspec(noinline)** belirli üye işlevi (işlevi bir sınıfa) hiçbir zaman satır içi derleyiciye bildirir.  
  
 Küçük ve kodunuzun performansını artırmak için kritik ise satır için bir işlev faydalı olabilir. Diğer bir deyişle, işlev, küçük ve sık sık çağrılacak olası değil ise, bir işlev gibi bir hata durumu işler.  
  
 Aklınızda bir işlev işaretlenmişse **noinline**, çağıran işlevin daha küçük ve bu nedenle, kendisi için satır içi derleyici bir aday olacaktır.  
  
```cpp 
class X {  
   __declspec(noinline) int mbrfunc() {  
      return 0;   
   }   // will not inline  
};  
```  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Satır içi, __inline, \__forceinline](inline-functions-cpp.md)

