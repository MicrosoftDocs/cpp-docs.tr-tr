---
title: Derleyici Hatası C2662 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2662
dev_langs:
- C++
helpviewer_keywords:
- C2662
ms.assetid: e172c2a4-f29e-4034-8232-e7dc6f83689f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e794f50dd6a23101e004618468b432c8969e54b5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042071"
---
# <a name="compiler-error-c2662"></a>Derleyici Hatası C2662

'function': 'this' işaretçisi 'type1' öğesinden 'type2' öğesine dönüştürülemiyor

Derleyici değil dönüştüremedi `this` işaretçisinden `type1` için `type2`.

Bu hata olmayan bir çağırarak kaynaklanabilir`const` üzerinde üye işlevi bir `const` nesne.  Olası çözümler:

- Kaldırma `const` gelen nesne bildirimi.

- Ekleme `const` üye işlevi.

Aşağıdaki örnek, C2662 oluşturur:

```
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

İle derlerken **/CLR**, bir işlev çağrılamaz bir `const` veya `volatile` tam yönetilen türü. Const yönetilen nesneler üzerinde yöntemlerini çağıramazsınız şekilde bir const yönetilen bir sınıf üyesi işlevi bildiremezsiniz.

```
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

Aşağıdaki örnek, C2662 oluşturur:

```
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