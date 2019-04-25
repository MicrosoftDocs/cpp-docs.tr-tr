---
title: Derleyici Hatası C2166
ms.date: 11/04/2016
f1_keywords:
- C2166
helpviewer_keywords:
- C2166
ms.assetid: 12789c3a-cc76-48bb-ae2e-64283e0964ed
ms.openlocfilehash: 36b4bcbd3eda213b840194cb635172a241f04b14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174725"
---
# <a name="compiler-error-c2166"></a>Derleyici Hatası C2166

lvalue, const nesnesi belirtiyor.

Kod öğesi bildirilmiş bir değiştirme girişiminde `const`.

Aşağıdaki örnek, C2166 oluşturur:

```
// C2166.cpp
int f();
int main() {
   ( (const int&) 1 ) = 5;   // C2166
}
```