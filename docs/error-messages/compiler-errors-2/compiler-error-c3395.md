---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3395'
title: Derleyici hatası C3395
ms.date: 11/04/2016
f1_keywords:
- C3395
helpviewer_keywords:
- C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
ms.openlocfilehash: 65db71a9dbc076b21d16f3f0c250c20a9b283daa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321975"
---
# <a name="compiler-error-c3395"></a>Derleyici hatası C3395

' function ': __declspec (dllexport) \_ _clrcall çağırma kuralına sahip bir işleve uygulanamaz

`__declspec(dllexport)` ve [__clrcall](../../cpp/clrcall.md) uyumlu değildir.  Daha fazla bilgi için bkz. [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

Aşağıdaki örnek C3395 oluşturur:

```cpp
// C3395.cpp
// compile with: /clr /c

__declspec(dllexport) void __clrcall Test(){}   // C3395
void __clrcall Test2(){}   // OK
__declspec(dllexport) void Test3(){}   // OK
```
