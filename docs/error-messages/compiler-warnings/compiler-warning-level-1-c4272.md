---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4272'
title: Derleyici Uyarısı (düzey 1) C4272
ms.date: 11/04/2016
f1_keywords:
- C4272
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
ms.openlocfilehash: a44e3a4121c1d01b15af47b0b4eefb1f982423bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266123"
---
# <a name="compiler-warning-level-1-c4272"></a>Derleyici Uyarısı (düzey 1) C4272

' function ': __declspec (dllimport) olarak işaretlenmiş; bir işlev içeri aktarılırken yerel çağırma kuralı belirtilmelidir.

[__Clrcall](../../cpp/clrcall.md) çağırma kuralına sahip bir işlevi dışarı aktarmak hatadır ve bir işlevi içeri aktarmaya çalışırsanız derleyici bu uyarıyı yayınlar `__clrcall` .

Aşağıdaki örnek C4272 oluşturur:

```cpp
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```
