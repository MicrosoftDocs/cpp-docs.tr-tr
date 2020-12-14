---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2496'
title: Derleyici hatası C2496
ms.date: 11/04/2016
f1_keywords:
- C2496
helpviewer_keywords:
- C2496
ms.assetid: 9a25237d-5bbb-4112-98f3-29cd99d3f89f
ms.openlocfilehash: da03162e5ba674267df25463a27f08f3f6032e70
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283711"
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
