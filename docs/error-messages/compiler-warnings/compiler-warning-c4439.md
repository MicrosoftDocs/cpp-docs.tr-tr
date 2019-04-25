---
title: Derleyici Uyarısı C4439
ms.date: 11/04/2016
f1_keywords:
- C4439
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
ms.openlocfilehash: d604c234b9445a7e5304118124620f0057f30975
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311351"
---
# <a name="compiler-warning-c4439"></a>Derleyici Uyarısı C4439

'function': imzasında yönetilen bir tür olan işlev tanımında bir __clrcall çağrı kuralı olması gerekir

Derleyici örtük olarak bir çağırma kuralı ile değiştirilen [__clrcall](../../cpp/clrcall.md). Bu uyarıyı çözmek için kaldırma `__cdecl` veya `__stdcall` çağırma kuralı.

C4439 her zaman hata olarak verilir. Bu uyarı ile kapatabilirsiniz `#pragma warning` veya **/wd**; bkz [uyarı](../../preprocessor/warning.md) veya [/w, /W0, / W1, / w2, / W3, / W4, / W1, / w2, / W3, / W4, /Wall, WD, / we Wo, wv, /WX (uyarı düzeyi)](../../build/reference/compiler-option-warning-level.md)daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4439 oluşturur.

```
// C4439.cpp
// compile with: /clr
void __stdcall f( System::String^ arg ) {}   // C4439
void __clrcall f2( System::String^ arg ) {}   // OK
void f3( System::String^ arg ) {}   // OK
```