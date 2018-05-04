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
ms.openlocfilehash: 1f81ab892fd7f406292925f424bebc7514fd7ea0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="noinline"></a>noinline
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 **__declspec(noinline)** hiçbir zaman satır içi derleyiciye belirli üye işlevi (bir sınıf işlevinde) söyler.  
  
 Küçük ve kodunuzu performansını artırmak için kritik ise değil satır içi işlev faydalı olabilir. Diğer bir deyişle, işlev küçük ve genellikle çağrılacak olası değil ise, bir işlev gibi bir hata koşulu işler.  
  
 Aklınızda işlevi işaretlenmişse `noinline`, çağıran işlevi daha küçük ve bu nedenle, kendisini derleyici satır içi kullanım aday olacaktır.  
  
```  
class X {  
   __declspec(noinline) int mbrfunc() {  
      return 0;   
   }   // will not inline  
};  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Satır içi, __inline, \__forceinline](inline-functions-cpp.md)

