---
title: Derleyici Uyarısı (düzey 1) C4272
ms.date: 11/04/2016
f1_keywords:
- C4272
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
ms.openlocfilehash: 13c56c2261cd069e7edec63921c198e2bee56c95
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626693"
---
# <a name="compiler-warning-level-1-c4272"></a>Derleyici Uyarısı (düzey 1) C4272

' function ': __declspec (dllimport) olarak işaretlenmiş; bir işlev içeri aktarılırken yerel çağırma kuralı belirtilmelidir.

[__Clrcall](../../cpp/clrcall.md) çağrı kuralına sahip işaretlenmiş bir işlevi dışarı aktarmak hatadır ve `__clrcall`olarak işaretlenmiş bir işlevi içeri aktarmaya çalışırsanız derleyici bu uyarıyı yayınlar.

Aşağıdaki örnek C4272 oluşturur:

```cpp
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```