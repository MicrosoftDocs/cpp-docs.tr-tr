---
title: Derleyici hatası C2124
ms.date: 11/04/2016
f1_keywords:
- C2124
helpviewer_keywords:
- C2124
ms.assetid: 93392aaa-5582-4d68-8cc5-bd9c62a0ae7e
ms.openlocfilehash: 5da04b100fdeaebb6b07d3f8c01e5ec8341ae1cf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748248"
---
# <a name="compiler-error-c2124"></a>Derleyici hatası C2124

sıfıra bölme veya mod

Sabit bir ifadede sıfır paydası vardır. Hatayı gidermek için sıfıra bölmeyin.

Aşağıdaki örnek C2124 oluşturur:

```cpp
// C2124.cpp
int main() {
  int i = 1 / 0;   // C2124  do not divide by zero
  int i2 = 12 / 2;   // OK
}
```
