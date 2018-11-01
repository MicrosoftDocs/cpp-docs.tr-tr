---
title: managed, unmanaged
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.unmanaged
- managed_CPP
- unmanaged_CPP
- vc-pragma.managed
helpviewer_keywords:
- managed pragma
- pragmas, unmanaged
- pragmas, managed
- unmanaged pragma
ms.assetid: f072ddcc-e1ec-408a-8ce1-326ddb60e4a4
ms.openlocfilehash: 0cc253ad7d0d4529340a13546f931075b0c7dfdc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473833"
---
# <a name="managed-unmanaged"></a>managed, unmanaged
Derleme yönetilen veya yönetilmeyen olarak işlevler için işlev düzeyi denetimi etkinleştirin.

## <a name="syntax"></a>Sözdizimi

```
#pragma managed
#pragma unmanaged
#pragma managed([push,] on | off)
#pragma managed(pop)
```

## <a name="remarks"></a>Açıklamalar

[/CLR](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği, yönetilen veya yönetilmeyen olarak işlevleri derlemek için Modül düzeyinde denetim sağlar.

Yönetilmeyen bir işlev için yerel platform derlenir ve söz konusu bölümü programın yürütülmesini ortak dil çalışma zamanı tarafından yerel platformuna geçirilecektir.

İşlevler, varsayılan olarak yönetilen olarak derlenir, `/clr` kullanılır.

Bu pragmaları uygularken:

- Önceki bir işlev pragması ekleyin, ancak bir işlev gövdesinin içinde değil.

- Ekleme pragmadan sonraki `#include` deyimleri. Önce bu pragmaları kullanmayın `#include` deyimleri.

Derleyicinin yoksaydığı **yönetilen** ve **yönetilmeyen** pragmalar, `/clr` derlemede kullanılmaz.

Bir şablonu işlev örneği oluşturulduğunda şablon tanımlarında zaman pragma durumunu, yönetilen yönetilmeyen mi olduğunu belirler.

Daha fazla bilgi için [karışık derlemeleri başlatma](../dotnet/initialization-of-mixed-assemblies.md).

## <a name="example"></a>Örnek

```cpp
// pragma_directives_managed_unmanaged.cpp
// compile with: /clr
#include <stdio.h>

// func1 is managed
void func1() {
   System::Console::WriteLine("In managed function.");
}

// #pragma unmanaged
// push managed state on to stack and set unmanaged state
#pragma managed(push, off)

// func2 is unmanaged
void func2() {
   printf("In unmanaged function.\n");
}

// #pragma managed
#pragma managed(pop)

// main is managed
int main() {
   func1();
   func2();
}
```

```Output
In managed function.
In unmanaged function.
```

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)