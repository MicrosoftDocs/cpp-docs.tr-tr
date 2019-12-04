---
title: Derleyici hatası C2791
ms.date: 11/04/2016
f1_keywords:
- C2791
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
ms.openlocfilehash: d589094f117135474d1a8788867d2d571bbb5f5d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739551"
---
# <a name="compiler-error-c2791"></a>Derleyici hatası C2791

geçersiz ' Super ' kullanımı: ' class ' herhangi bir taban sınıfa sahip değil

[Super](../../cpp/super.md) anahtar sözcüğü, temel sınıfı olmayan bir sınıfın üye işlevinin bağlamı içinde kullanıldı.

Aşağıdaki örnek C2791 oluşturur:

```cpp
// C2791.cpp
struct D {
   void mf() {
      __super::mf();   // C2791
   }
};
```
