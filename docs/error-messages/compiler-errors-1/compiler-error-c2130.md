---
title: Derleyici hatası C2130
ms.date: 11/04/2016
f1_keywords:
- C2130
helpviewer_keywords:
- C2130
ms.assetid: c6fd5a7e-8f28-4f67-99d1-95a13b0dff90
ms.openlocfilehash: 591ff7bae42c43621d9c5bea1ae42da46d341b48
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755167"
---
# <a name="compiler-error-c2130"></a>Derleyici hatası C2130

\#satırı dosya adını içeren bir dize bekliyordu, ' token ' bulundu

[#Line](../../preprocessor/hash-line-directive-c-cpp.md) `linenumber` aşağıdaki isteğe bağlı dosya adı belirteci bir dize olmalıdır.

Aşağıdaki örnek C2130 oluşturur:

```cpp
// C2130.cpp
int main() {
   #line 1000 test   // C2130
   #line 1000 "test"   // OK
}
```
