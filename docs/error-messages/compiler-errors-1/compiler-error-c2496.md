---
title: Derleyici hatası C2496
ms.date: 11/04/2016
f1_keywords:
- C2496
helpviewer_keywords:
- C2496
ms.assetid: 9a25237d-5bbb-4112-98f3-29cd99d3f89f
ms.openlocfilehash: 9236876e636e88f193d32ef2e33a817fa52e1bd2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757013"
---
# <a name="compiler-error-c2496"></a>Derleyici hatası C2496

' tanımlayıcı ': ' selectany ' yalnızca dış bağlantıya sahip veri öğelerine uygulanabilir

[Selectany](../../cpp/selectany.md) özniteliği yalnızca dışarıdan görünür ve genel veri öğelerine uygulanabilir.

Aşağıdaki örnek C2496 oluşturur:

```cpp
// C2496.cpp
// compile with: /c
__declspec(selectany) int x1 = 1;
const __declspec(selectany) int x2 = 2;   // C2496
static __declspec(selectany) int x6 = 6;   // C2496

extern const __declspec(selectany) int x3 = 3;

__declspec(selectany) int x4;

// dynamic initialization of x5
int f();
__declspec(selectany) int x5 = f();

extern const int x7;
// OK - redeclaration of x7 that is extern
const __declspec(selectany) int x7 = 7;
```
