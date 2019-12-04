---
title: Derleyici hatası C3740
ms.date: 11/04/2016
f1_keywords:
- C3740
helpviewer_keywords:
- C3740
ms.assetid: edb17a90-2307-4df6-943d-580460d26d2b
ms.openlocfilehash: 4e32c37853f4c877e6260e38daa0c8357ca54a25
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752671"
---
# <a name="compiler-error-c3740"></a>Derleyici hatası C3740

Şablonlar, olayları kaynak veya alamaz

Şablonlu bir sınıf veya yapı [olay](../../cpp/event-handling.md)içeremez.

Aşağıdaki örnek C3740 oluşturur:

```cpp
// C3740.cpp
template <typename T>   // Delete the template specification
struct E {
   __event void f();   // C3740
};

int main() {
}
```
