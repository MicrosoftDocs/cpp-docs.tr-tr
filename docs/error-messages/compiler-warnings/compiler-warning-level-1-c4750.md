---
title: Derleyici Uyarısı (düzey 1) C4750 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4750
dev_langs:
- C++
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ffe378f8d2466e702c90127e44f3b48831abf50
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4750"></a>Derleyici Uyarısı (düzey 1) C4750
'tanımlayıcısı': _alloca() bir döngüye içermesinden ile işlevi  
  
 'Tanımlayıcısı' işlevi, satır içi genişletme zorlar [_alloca](../../c-runtime-library/reference/alloca.md) döngüsü çalıştırıldığında bir yığın taşması neden bir döngüsü içinde işlevi.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  'Tanımlayıcısı' işlevi ile değiştirilmez olun [__forceinline](../../cpp/inline-functions-cpp.md) tanımlayıcısı.  
  
2.  'Tanımlayıcısı' işlevi içermez olun bir [_alloca](../../c-runtime-library/reference/alloca.md) bir Döngüdeki işlevi.  
  
3.  Belirtmeyin [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/Ox](../../build/reference/ox-full-optimization.md), veya [/Og](../../build/reference/og-global-optimizations.md) derleme anahtar.  
  
4.  Yer [_alloca](../../c-runtime-library/reference/alloca.md) işlevi bir [deneyin-except deyimi](../../cpp/try-except-statement.md) bir yığın taşması catch.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği çağrıları `MyFunction` , döngü ve `MyFunction` çağrıları `_alloca` işlevi. `__forceinline` Değiştiricisi neden olan satır içi genişlemesi `_alloca` işlevi.  
  
```  
// c4750.cpp  
// compile with: /O2 /W1 /c  
#include <intrin.h>  
  
char * volatile newstr;  
  
__forceinline void myFunction(void) // C4750 warning  
{  
// The _alloca function does not require a __try/__except   
// block because the example uses compiler option /c.  
    newstr = (char * volatile) _alloca(1000);  
}  
  
int main(void)  
{  
    for (int i=0; i<50000; i++)  
       myFunction();  
    return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_alloca](../../c-runtime-library/reference/alloca.md)