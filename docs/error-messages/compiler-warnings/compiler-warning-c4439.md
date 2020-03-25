---
title: Derleyici Uyarısı C4439
ms.date: 11/04/2016
f1_keywords:
- C4439
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
ms.openlocfilehash: c125fa84119c62e3090611c9a841f46eee759711
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165216"
---
# <a name="compiler-warning-c4439"></a>Derleyici Uyarısı C4439

' function ': İmzada yönetilen bir tür olan işlev tanımı __clrcall çağrı kuralına sahip olmalıdır

Derleyici bir çağırma kuralını örtük olarak [__clrcall](../../cpp/clrcall.md)ile değiştirdi. Bu uyarıyı çözmek için `__cdecl` veya çağırma kuralını `__stdcall` kaldırın.

C4439 her zaman bir hata olarak verilir. Bu uyarıyı `#pragma warning` veya **/WD**; ile devre dışı bırakabilirsiniz. daha fazla bilgi için bkz. [Warning](../../preprocessor/warning.md) [;/W,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/duvar,/WD,/we,/Wo,/WV,/WX (uyarı düzeyi)](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4439 oluşturur.

```cpp
// C4439.cpp
// compile with: /clr
void __stdcall f( System::String^ arg ) {}   // C4439
void __clrcall f2( System::String^ arg ) {}   // OK
void f3( System::String^ arg ) {}   // OK
```
