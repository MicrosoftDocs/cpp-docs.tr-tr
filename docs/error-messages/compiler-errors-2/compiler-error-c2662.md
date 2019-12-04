---
title: Derleyici hatası C2662
ms.date: 11/04/2016
f1_keywords:
- C2662
helpviewer_keywords:
- C2662
ms.assetid: e172c2a4-f29e-4034-8232-e7dc6f83689f
ms.openlocfilehash: b2fa2643898fed510aa7cf0f483b538ebb33b033
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760458"
---
# <a name="compiler-error-c2662"></a>Derleyici hatası C2662

' function ': ' this ' işaretçisi ' type1 ' iken ' type2 ' olarak dönüştürülemez

Derleyici `type1` `this` işaretçisini `type2`dönüştüremedi.

Bu hata, bir `const` nesnesi üzerinde`const` olmayan bir üye işlevi çağırarak oluşabilir.  Olası çözümler:

- Nesne bildiriminden `const` kaldırın.

- Üye işlevine `const` ekleyin.

Aşağıdaki örnek C2662 oluşturur:

```cpp
// C2662.cpp
class C {
public:
   void func1();
   void func2() const{}
} const c;

int main() {
   c.func1();   // C2662
   c.func2();   // OK
}
```

**/Clr**ile derlerken, `const` veya `volatile` nitelikli yönetilen tür üzerinde bir işlev çağrılamaz. Yönetilen bir sınıfın const üye işlevini bildiremezsiniz, bu nedenle const yönetilen nesneler üzerinde Yöntemler çağrılamaz.

```cpp
// C2662_b.cpp
// compile with: /c /clr
ref struct M {
   property M^ Type {
      M^ get() { return this; }
   }

   void operator=(const M %m) {
      M ^ prop = m.Type;   // C2662
   }
};

ref struct N {
   property N^ Type {
      N^ get() { return this; }
   }

   void operator=(N % n) {
      N ^ prop = n.Type;   // OK
   }
};
```

Aşağıdaki örnek C2662 oluşturur:

```cpp
// C2662_c.cpp
// compile with: /c
// C2662 expected
typedef int ISXVD;
typedef unsigned char BYTE;

class LXBASE {
protected:
    BYTE *m_rgb;
};

class LXISXVD:LXBASE {
public:
   // Delete the following line to resolve.
   ISXVD *PMin() { return (ISXVD *)m_rgb; }

   ISXVD *PMin2() const { return (ISXVD *)m_rgb; };   // OK
};

void F(const LXISXVD *plxisxvd, int iDim) {
   ISXVD isxvd;
   // Delete the following line to resolve.
   isxvd = plxisxvd->PMin()[iDim];

   isxvd = plxisxvd->PMin2()[iDim];
}
```
