---
title: Derleyici hatası C3612
ms.date: 11/04/2016
f1_keywords:
- C3612
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
ms.openlocfilehash: 499c31b0c02bd72695cd6118612609a70316f0ae
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755752"
---
# <a name="compiler-error-c3612"></a>Derleyici hatası C3612

' Type ': Sealed bir sınıf abstract olamaz

`value` kullanılarak tanımlanan türler varsayılan olarak korumalıdır ve temel aldığı tüm yöntemleri uygulamadıkça bir sınıf soyuttur. Sealed bir soyut sınıf, temel sınıf olamaz, ya da oluşturulabilir.

Daha fazla bilgi için bkz. [sınıflar ve yapılar](../../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3612 oluşturur:

```cpp
// C3612.cpp
// compile with: /clr /c
value struct V: public System::ICloneable {};   // C3612

// OK
value struct V2: public System::ICloneable {
   Object^ Clone();
};
```
