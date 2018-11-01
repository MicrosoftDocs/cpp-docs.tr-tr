---
title: Derleyici Hatası C3395
ms.date: 11/04/2016
f1_keywords:
- C3395
helpviewer_keywords:
- C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
ms.openlocfilehash: 2e5234abcbe46e17035fd0b16e9816c879d86cfe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604139"
---
# <a name="compiler-error-c3395"></a>Derleyici Hatası C3395

'function': __declspec(dllexport), bulunan bir fonksiyona uygulanamaz \__clrcall çağırma kuralı

`__declspec(dllexport)` ve [__clrcall](../../cpp/clrcall.md) uyumlu değildir.  Daha fazla bilgi için [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

Aşağıdaki örnek, C3395 oluşturur:

```
// C3395.cpp
// compile with: /clr /c

__declspec(dllexport) void __clrcall Test(){}   // C3395
void __clrcall Test2(){}   // OK
__declspec(dllexport) void Test3(){}   // OK
```