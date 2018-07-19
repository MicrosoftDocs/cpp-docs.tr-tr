---
title: __restrict | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __restrict_cpp
dev_langs:
- C++
helpviewer_keywords:
- __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e402fc9a32b92960f251796365199a608d6d1137
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948258"
---
# <a name="restrict"></a>__restrict
Gibi **__declspec ( [kısıtlama](../cpp/restrict.md) )** değiştiricisi **__restrict** anahtar sözcüğü gösteren bir simge geçerli kapsamda diğer adı değil. **__Restrict** anahtar sözcüğünden farklıdır `__declspec ( restrict )` aşağıdaki yollarla değiştiricisi:  
  
-   **__Restrict** anahtar sözcüğü yalnızca değişkenler üzerinde geçerlidir ve `__declspec ( restrict )` yalnızca işlev bildirimleri ve tanımları üzerinde geçerlidir.  
  
-   **__restrict** benzer **kısıtlama** C99 belirtimi gelen ancak **__restrict** C ya da C++ programlarında kullanılabilir.  
  
-   Zaman **__restrict** olan kullanıldığında, derleyici değişkenin diğer ad olmayan özelliğini yaymayacaktır. Diğer bir deyişle, atarsanız bir **__restrict** olmayan bir değişken **__restrict** değişken, derleyici hala sağlayacak __restrict olmayan değişkenine diğer adı olması. Bu davranışından farklıdır **kısıtlama** C99 belirtimindeki from anahtar sözcüğü.  
  
 Tüm işlevin davranışını etkilerseniz, genellikle bunu kullanmak en iyisidir `__declspec ( restrict )` daha anahtar sözcüğü.  
  
 Visual Studio 2015 ve sonraki sürümlerinde, **__restrict** C++ başvuruları üzerinde kullanılabilir.  
  
> [!NOTE]
>  Ayrıca bir değişken üzerinde kullanıldığında [geçici](../cpp/volatile-cpp.md) anahtar sözcüğü, **geçici** öncelikli olur.  
  
## <a name="example"></a>Örnek  
  
```cpp 
// __restrict_keyword.c  
// compile with: /LD  
// In the following function, declare a and b as disjoint arrays  
// but do not have same assurance for c and d.  
void sum2(int n, int * __restrict a, int * __restrict b,   
          int * c, int * d) {  
   int i;  
   for (i = 0; i < n; i++) {  
      a[i] = b[i] + c[i];  
      c[i] = b[i] + d[i];  
    }  
}  
  
// By marking union members as __restrict, tell compiler that  
// only z.x or z.y will be accessed in any given scope.  
union z {  
   int * __restrict x;  
   double * __restrict y;  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)