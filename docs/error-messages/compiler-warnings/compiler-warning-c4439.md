---
title: Derleyici Uyarısı C4439
ms.date: 11/04/2016
f1_keywords:
- C4439
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
ms.openlocfilehash: baf74733c94fdb03f130d2300d0918845cc4de4c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223336"
---
# <a name="compiler-warning-c4439"></a>Derleyici Uyarısı C4439

' function ': İmzada yönetilen bir tür olan işlev tanımı __clrcall çağrı kuralına sahip olmalıdır

Derleyici bir çağırma kuralını örtük olarak ile değiştirdi [`__clrcall`](../../cpp/clrcall.md) . Bu uyarıyı çözmek için **`__cdecl`** veya **`__stdcall`** çağırma kuralını kaldırın.

C4439 her zaman bir hata olarak verilir. Bu uyarıyı veya ile devre dışı bırakabilirsiniz `#pragma warning` **`/wd`** ; daha fazla bilgi için bkz. [Warning](../../preprocessor/warning.md) veya [/W,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/duvar,/WD,/we,/Wo,/WV,/WX (uyarı düzeyi)](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4439 oluşturur.

```cpp
// C4439.cpp
// compile with: /clr
void __stdcall f( System::String^ arg ) {}   // C4439
void __clrcall f2( System::String^ arg ) {}   // OK
void f3( System::String^ arg ) {}   // OK
```
