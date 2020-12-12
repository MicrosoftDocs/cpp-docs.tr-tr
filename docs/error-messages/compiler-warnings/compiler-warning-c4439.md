---
description: 'Hakkında daha fazla bilgi edinin: derleyici uyarısı C4439'
title: Derleyici Uyarısı C4439
ms.date: 11/04/2016
f1_keywords:
- C4439
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
ms.openlocfilehash: 123f42ca495faeccc995dc1ac87572180d1dce70
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180753"
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
