---
title: Derleyici Uyarısı (düzey 1) C4488
ms.date: 11/04/2016
f1_keywords:
- C4488
helpviewer_keywords:
- C4488
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
ms.openlocfilehash: c816c1b3f5481ccff19fd2a2377c5fc98f950fee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577833"
---
# <a name="compiler-warning-level-1-c4488"></a>Derleyici Uyarısı (düzey 1) C4488

'function': 'interface_method' arabirim yöntemini uygulamak için 'anahtar sözcüğü' anahtar sözcüğünü gerektiriyor

Bir sınıf tüm üyelerini doğrudan devraldığı arabirim uygulamalıdır. Uygulanan bir üye, genel erişilebilirliği olmalıdır ve sanal olarak işaretlenmelidir.

## <a name="example"></a>Örnek

C4488 uygulanan bir üyesi genel olmadığından ortaya çıkabilir. Aşağıdaki örnek, C4488 oluşturur.

```
// C4488.cpp
// compile with: /clr /c /W1 /WX
interface struct MyI {
   void f1();
};

// implemented member not public
ref class B : MyI { virtual void f1() {} };  // C4488

// OK
ref class C : MyI {
public:
   virtual void f1() {}
};
```

## <a name="example"></a>Örnek

Uygulanan bir üye sanal işaretlenmemişse C4488 ortaya çıkabilir. Aşağıdaki örnek, C4488 oluşturur.

```
// C4488_b.cpp
// compile with: /clr /c /W1 /WX
interface struct MyI {
   void f1();
};

ref struct B : MyI { void f1() {} };   // C4488
ref struct C : MyI { virtual void f1() {} };   // OK
```