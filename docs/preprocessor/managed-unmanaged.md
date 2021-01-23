---
description: Microsoft C++ ' da yönetilen ve yönetilmeyen yönergeler hakkında daha fazla bilgi edinin pragma
title: yönetilen ve yönetilmeyen pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.unmanaged
- managed_CPP
- unmanaged_CPP
- vc-pragma.managed
helpviewer_keywords:
- managed pragma
- pragma, unmanaged
- pragma, managed
- unmanaged pragma
no-loc:
- pragma
ms.openlocfilehash: a106e9a1370daeedb94bbf5e4d092ae85457a3d2
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713512"
---
# <a name="managed-and-unmanaged-no-locpragma"></a>`managed`ve `unmanaged`pragma

İşlevleri yönetilen veya yönetilmeyen olarak derlemek için işlev düzeyi denetimini etkinleştirin.

## <a name="syntax"></a>Syntax

> **`#pragma managed`**\
> **`#pragma unmanaged`**\
> **`#pragma managed(`** [ **`push,`** ] { **`on`** | **`off`** } **`)`**\
> **`#pragma managed(pop)`**

## <a name="remarks"></a>Açıklamalar

[`/clr`](../build/reference/clr-common-language-runtime-compilation.md)Derleyici seçeneği, işlevleri yönetilen veya yönetilmeyen olarak derlemek için modül düzeyinde denetim sağlar.

Yönetilmeyen bir işlev yerel platform için derlenir. Programın bu bölümünün yürütülmesi, ortak dil çalışma zamanı tarafından yerel platforma geçirilir.

İşlevler, kullanıldığında varsayılan olarak yönetilen olarak derlenir **`/clr`** .

**`managed`** Veya uygulanırken **`unmanaged`** pragma :

- pragmaÖnceki bir işlevi ekleyin, ancak işlev gövdesi içinde değil.

- pragmaAfter deyimlerini ekleyin `#include` . Hiçbir deyimden önce kullanmayın `#include` .

Derleyici, **`managed`** **`unmanaged`** pragma **`/clr`** derleme içinde kullanılmıyorsa, ve öğesini yoksayar.

Bir şablon işlevi örneği oluşturulduğunda, pragma şablon tanımlandığında durum yönetilip yönetilmediğini belirler.

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

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
