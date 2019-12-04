---
title: Derleyici hatası C3395
ms.date: 11/04/2016
f1_keywords:
- C3395
helpviewer_keywords:
- C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
ms.openlocfilehash: eaf63b42a6c44153a55d8aeb70f4f1174a5c895c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737549"
---
# <a name="compiler-error-c3395"></a>Derleyici hatası C3395

' function ': __declspec (dllexport) \__clrcall çağırma kuralına sahip bir işleve uygulanamaz

`__declspec(dllexport)` ve [__clrcall](../../cpp/clrcall.md) uyumlu değildir.  Daha fazla bilgi için bkz. [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

Aşağıdaki örnek C3395 oluşturur:

```cpp
// C3395.cpp
// compile with: /clr /c

__declspec(dllexport) void __clrcall Test(){}   // C3395
void __clrcall Test2(){}   // OK
__declspec(dllexport) void Test3(){}   // OK
```
