---
title: _ReturnAddress | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _ReturnAddress
dev_langs:
- C++
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0431302ae745a1e4a03da4b3fd660fda7d2cfa72
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333176"
---
# <a name="returnaddress"></a>_ReturnAddress
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 `_ReturnAddress` İç arama işlevinde denetim çağırana döndükten sonra yürütülecek yönerge adresi sağlar.  
  
 Yapı aşağıdaki programı ve hata ayıklayıcı adım adım ilerleyin. Program aracılığıyla adım olarak, sunucudan döndürülen adresini Not `_ReturnAddress`. İşlevinden döndürmeden sonra hemen sonra burada `_ReturnAddress` kullanılan, açık olan [nasıl yapılır: Ayrıştırılmış kod penceresini kullanma](/visualstudio/debugger/how-to-use-the-disassembly-window) ve yürütülecek sonraki yönerge adresi döndürülenadresiyleeşleşenNot`_ReturnAddress`.  
  
 Satır içi kullanım may gibi iyileştirmeler dönüş adresi etkiler. Örneğin, aşağıdaki örnek program ile derlenmiş [/Ob1](../build/reference/ob-inline-function-expansion.md), `inline_func` tabloya çağıran işlev, satır içi olacaktır `main`. Bu nedenle, çağrıları `_ReturnAddress` gelen `inline_func` ve `main` her aynı değeri oluşturur.  
  
 Zaman `_ReturnAddress` ile derlenen bir programda kullanılan [/CLR](../build/reference/clr-common-language-runtime-compilation.md), işlevi içeren `_ReturnAddress` çağrısı, yerel bir işlevi olarak derlenmiş. Ne zaman bir işlevi olarak derlenmiş yönetilen işlevi içeren içine çağrıları `_ReturnAddress`, `_ReturnAddress` beklendiği gibi çalışmayabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="example"></a>Örnek  
  
```  
// compiler_intrinsics__ReturnAddress.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_ReturnAddress)  
  
__declspec(noinline)  
void noinline_func(void)  
{  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
}  
  
__forceinline  
void inline_func(void)  
{  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
}  
  
int main(void)  
{  
   noinline_func();   
   inline_func();  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
  
   return 0;  
}  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)   
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)