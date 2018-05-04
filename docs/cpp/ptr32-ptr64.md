---
title: __ptr32, __ptr64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53fafb1e7be45cd4b48ce51e787b6338dd0f7324
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 `__ptr32` yerel bir işaretçi bir 32 bit sistemdeki temsil ederken `__ptr64` yerel bir işaretçi bir 64-bit sistemde temsil eder.  
  
 Aşağıdaki örnek, bu işaretçi türleri bildirme gösterilmektedir:  
  
```  
int * __ptr32 p32;  
int * __ptr64 p64;  
```  
  
 İle bir işaretçi bir 32 bit sistemde bildirilen `__ptr64` 32-bit işaretçi kesilir. İle bir işaretçi bir 64-bit sistemde bildirilen `__ptr32` bir 64-bit işaretçi yüklenen.  
  
> [!NOTE]
>  Kullanamazsınız `__ptr32` veya `__ptr64` ile derleme yapılırken **/CLR: pure**. Aksi takdirde `Compiler Error C2472` oluşturulur. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bildirme ve işaretçileri ile tahsis gösterilmektedir `__ptr32` ve `__ptr64` anahtar sözcükler.  
  
```  
#include <cstdlib>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    int * __ptr32 p32;  
    int * __ptr64 p64;  
  
    p32 = (int * __ptr32)malloc(4);  
    *p32 = 32;  
    cout << *p32 << endl;  
  
    p64 = (int * __ptr64)malloc(4);  
    *p64 = 64;  
    cout << *p64 << endl;  
}  
```  
  
```Output  
32  
64  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel Türler](../cpp/fundamental-types-cpp.md)