---
title: Derleyici hatası C3628
ms.date: 11/04/2016
f1_keywords:
- C3628
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
ms.openlocfilehash: 9976cb2425f8f855ffb2903c07de22822c781e20
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755830"
---
# <a name="compiler-error-c3628"></a>Derleyici hatası C3628

' temel sınıf ': yönetilen veya WinRTclasses yalnızca genel devralmayı destekler

Yönetilen veya WinRT sınıfı [özel](../../cpp/private-cpp.md) veya [korumalı](../../cpp/protected-cpp.md) bir temel sınıf olarak kullanılmaya çalışıldı. Yönetilen veya WinRT sınıfı, yalnızca [ortak](../../cpp/public-cpp.md) erişime sahip bir temel sınıf olarak kullanılabilir.

Aşağıdaki örnek C3628 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3628a.cpp
// compile with: /clr
ref class B {
};

ref class D : private B {   // C3628

// The following line resolves the error.
// ref class D : public B {
};

int main() {
}
```
