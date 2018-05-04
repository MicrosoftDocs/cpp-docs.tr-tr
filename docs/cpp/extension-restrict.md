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
ms.openlocfilehash: d96abd70990f1c01229004e9be000ec4e35a8595
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="restrict"></a>__restrict
Gibi **__declspec ( [kısıtlamak](../cpp/restrict.md) )** değiştiricisi, `__restrict` anahtar sözcüğü gösteren bir simge geçerli kapsamdaki diğer adı değil. `__restrict` anahtar sözcüğü, `__declspec ( restrict )` değiştiricisinden aşağıdaki şekilde farklıdır:  
  
-   `__restrict` anahtar sözcüğü yalnızca değişkenler üzerinde geçerlidir, `__declspec ( restrict )` ise yalnızca işlev bildirimleri ve tanımları üzerinde geçerlidir.  
  
-   `__restrict`, C99 belirtimindeki `restrict`'e benzerdir, ancak `__restrict` C ya da C++ programlarında kullanılabilir.  
  
-   `__restrict` kullanıldığında, derleyici değişkenin diğer ad olmayan özelliğini yaymayacaktır. Diğer bir deyişle, eğer atarsanız bir `__restrict` için olmayan bir değişken`__restrict` değişken, derleyici hala sağlayacak __restrict olmayan diğer adı olması için değişken. Bu, C99 belirtimindeki `restrict` anahtar sözcüğünün davranışından farklıdır.  
  
 Tüm işlevi davranışını etkilerse, genellikle, bunu kullanmak en iyisidir `__declspec ( restrict )` anahtar sözcüğü'den.  
  
 Visual Studio 2015 ve sonraki sürümlerinde, `__restrict` C++ başvuruları üzerinde kullanılabilir.  
  
> [!NOTE]
>  Ayrıca sahip bir değişken kullanıldığında [volatile](../cpp/volatile-cpp.md) anahtar sözcüğü, `volatile` öncelikli olur.  
  
## <a name="example"></a>Örnek  
  
```  
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