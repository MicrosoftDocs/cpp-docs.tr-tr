---
title: _ReturnAddress
ms.date: 09/02/2019
f1_keywords:
- _ReturnAddress
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
ms.openlocfilehash: 2a830ff1e8a2c9551dec52cf10a3d5cf126bde3b
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218052"
---
# <a name="_returnaddress"></a>_ReturnAddress

**Microsoft 'a özgü**

`_ReturnAddress` İç işlem, Denetim çağırana döndüğünde çalıştırılacak çağırma işlevindeki yönergenin adresini sağlar.

Aşağıdaki programı oluşturun ve hata ayıklayıcıda adım adım ilerleyin. Programda ilerlen, öğesinden `_ReturnAddress`döndürülen adresi unutmayın. Ardından, kullanıldığı `_ReturnAddress` [işlevden döndükten hemen sonra, nasıl yapılır: Ayrıştırma penceresini](/visualstudio/debugger/how-to-use-the-disassembly-window) kullanın ve yürütülecek sonraki yönergenin adresinin, öğesinden `_ReturnAddress`döndürülen adresle eşleştiğini unutmayın.

Satır içi gibi iyileştirmeler dönüş adresini etkileyebilir. Örneğin, aşağıdaki örnek program [/OB1](../build/reference/ob-inline-function-expansion.md)ile derlenirse, `inline_func` çağırma işlevinde `main`satır içine alınır. Bu nedenle, ve `_ReturnAddress` `main` ' dan `inline_func` öğesine yapılan çağrılar aynı değeri üretir.

/Clr ile derlenen bir programda kullanıldığında, [](../build/reference/clr-common-language-runtime-compilation.md) `_ReturnAddress` çağrıyı içeren işlev yerel bir işlev olarak derlenir. `_ReturnAddress` `_ReturnAddress` İçeren`_ReturnAddress` işleve yönetilen çağrı olarak derlenen bir işlev beklendiği gibi davranmayabilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<Intrin. h >

## <a name="example"></a>Örnek

```cpp
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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
