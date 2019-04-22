---
title: _ReturnAddress
ms.date: 11/04/2016
f1_keywords:
- _ReturnAddress
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
ms.openlocfilehash: e5013b20f9e7ed0349d940d9be61cc1b4afc95d4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041143"
---
# <a name="returnaddress"></a>_ReturnAddress

## <a name="microsoft-specific"></a>Microsoft'a Özgü

`_ReturnAddress` İç denetim çağırana döndükten sonra yürütülecek çağıran işlevin yönergenin adresi sağlar.

Aşağıdaki program ve hata ayıklayıcı adımlayabilir oluşturun. Program aracılığıyla ilerleyerek öğesinden döndürülen adresini not alın `_ReturnAddress`. Daha sonra işlevden döndüren hemen sonra nerede `_ReturnAddress` kullanılan, açık olan [nasıl yapılır: Ayrıştırılmış kod penceresini kullanma](/visualstudio/debugger/how-to-use-the-disassembly-window) ve yürütülecek sonraki yönerge adresini döndürüldüğü adresi eşleştiğini Not `_ReturnAddress`.

Satır içi kullanım Mayıs gibi iyileştirmeler dönüş adresi etkiler. Örneğin, aşağıdaki örnek program ile derlenmiş [/Ob1](../build/reference/ob-inline-function-expansion.md), `inline_func` çağıran işlevin alınmayacağı `main`. Bu nedenle, çağrıları `_ReturnAddress` gelen `inline_func` ve `main` her aynı değeri oluşturur.

Zaman `_ReturnAddress` ile derlenmiş bir program kullanılır [/CLR](../build/reference/clr-common-language-runtime-compilation.md), işlevi içeren `_ReturnAddress` yerel bir işlev çağrısı derlenecek. Ne zaman olarak bir işlev derlenmiş yönetilen işlevi içeren içine çağrıları `_ReturnAddress`, `_ReturnAddress` beklendiği gibi çalışmayabilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<intrin.h >

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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)