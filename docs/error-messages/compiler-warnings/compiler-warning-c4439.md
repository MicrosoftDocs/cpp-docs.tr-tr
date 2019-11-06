---
title: Derleyici Uyarısı C4439
ms.date: 11/04/2016
f1_keywords:
- C4439
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
ms.openlocfilehash: 7cab2e55fca640438051fbb79ac933e83d5f3cbb
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623651"
---
# <a name="compiler-warning-c4439"></a>Derleyici Uyarısı C4439

' function ': İmzada yönetilen bir tür olan işlev tanımında __clrcall çağrı kuralı olmalıdır

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