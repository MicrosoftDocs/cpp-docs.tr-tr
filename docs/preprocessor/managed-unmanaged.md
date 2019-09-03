---
title: managed, unmanaged pragmalar
ms.date: 08/29/2019
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
ms.openlocfilehash: 4c13155d1c84966a593df11baf525a0c3539f02c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218815"
---
# <a name="managed-unmanaged-pragmas"></a>managed, unmanaged pragmalar

İşlevleri yönetilen veya yönetilmeyen olarak derlemek için işlev düzeyi denetimini etkinleştirin.

## <a name="syntax"></a>Sözdizimi

> **#pragma yönetiliyor**\
> **#pragma yönetilmeyen**\
> **#pragma Managed (** [ **push,** ] { **on** | **off** } **)** \
> **#pragma Managed (pop)**

## <a name="remarks"></a>Açıklamalar

[/Clr](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği, işlevleri yönetilen veya yönetilmeyen olarak derlemek için modül düzeyinde denetim sağlar.

Yerel platform için yönetilmeyen bir işlev derlenir. Programın bu bölümünün yürütülmesi, ortak dil çalışma zamanı tarafından yerel platforma geçirilir.

İşlevler `/clr` , kullanıldığında varsayılan olarak yönetilen olarak derlenir.

Bu pragmalar uygulanırken:

- Bir işlev gövdesinde değil, önce pragma ' ı ekleyin.

- Pragma After `#include` deyimlerini ekleyin. Deyimlerden önce `#include` bu pragmaları kullanmayın.

Derleyici, derlemede kullanılmazsa **yönetilen** ve **yönetilmeyen** `/clr` pragmaları yoksayar.

Bir şablon işlevi örneği oluşturulduğunda, şablon tanımlandığında pragma durumu yönetilip yönetilmediğini belirler.

Daha fazla bilgi için bkz. [karışık derlemeleri başlatma](../dotnet/initialization-of-mixed-assemblies.md).

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

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
