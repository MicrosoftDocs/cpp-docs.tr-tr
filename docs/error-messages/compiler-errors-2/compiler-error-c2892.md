---
title: Derleyici hatası C2892
ms.date: 11/04/2016
f1_keywords:
- C2892
helpviewer_keywords:
- C2892
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
ms.openlocfilehash: f3868a44cf04d6c87092759ea473aa78aa0ad4c4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760895"
---
# <a name="compiler-error-c2892"></a>Derleyici hatası C2892

Yerel sınıfın üye şablonları olamaz

Şablonlu üye işlevleri, bir işlevde tanımlı bir sınıfta geçerli değildir.

Aşağıdaki örnek C2892 oluşturur:

```cpp
// C2892.cpp
int main() {
   struct local {
      template<class T>   // C2892
      void f() {}
   };
}
```
