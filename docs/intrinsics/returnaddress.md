---
description: 'Hakkında daha fazla bilgi edinin: _ReturnAddress'
title: _ReturnAddress
ms.date: 09/02/2019
f1_keywords:
- _ReturnAddress
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
ms.openlocfilehash: abb6b879c466372fce0ecbeb7371101e3a3ef82b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143747"
---
# <a name="_returnaddress"></a>_ReturnAddress

**Microsoft'a Özgü**

`_ReturnAddress`İç işlem, Denetim çağırana döndüğünde çalıştırılacak çağırma işlevindeki yönergenin adresini sağlar.

Aşağıdaki programı oluşturun ve hata ayıklayıcıda adım adım ilerleyin. Programda ilerlen, öğesinden döndürülen adresi unutmayın `_ReturnAddress` . Ardından, kullanıldığı işlevden döndükten hemen sonra, `_ReturnAddress` [nasıl yapılır: ayrıştırma penceresini](/visualstudio/debugger/how-to-use-the-disassembly-window) açın ve yürütülecek sonraki yönergenin adresinin, öğesinden döndürülen adresle eşleştiğini unutmayın `_ReturnAddress` .

Satır içi gibi iyileştirmeler dönüş adresini etkileyebilir. Örneğin, aşağıdaki örnek program [/OB1](../build/reference/ob-inline-function-expansion.md)ile derlenirse, `inline_func` çağırma işlevinde satır içine alınır `main` . Bu nedenle, ve ' dan öğesine yapılan çağrılar `_ReturnAddress` `inline_func` `main` aynı değeri üretir.

`_ReturnAddress` [/Clr](../build/reference/clr-common-language-runtime-compilation.md)ile derlenen bir programda kullanıldığında, çağrıyı içeren işlev `_ReturnAddress` yerel bir işlev olarak derlenir. İçeren işleve yönetilen çağrı olarak derlenen bir işlev `_ReturnAddress` `_ReturnAddress` beklendiği gibi davranmayabilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası**\<intrin.h>

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
[Anahtar sözcükler](../cpp/keywords-cpp.md)
