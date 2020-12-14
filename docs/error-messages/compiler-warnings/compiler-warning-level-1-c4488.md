---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4488'
title: Derleyici Uyarısı (düzey 1) C4488
ms.date: 11/04/2016
f1_keywords:
- C4488
helpviewer_keywords:
- C4488
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
ms.openlocfilehash: 60f72a76657e7661beb43441208dda3cddd26f48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310934"
---
# <a name="compiler-warning-level-1-c4488"></a>Derleyici Uyarısı (düzey 1) C4488

' function ': ' interface_method ' arabirim yöntemini uygulamak için ' anahtar sözcüğü ' anahtar sözcüğünü gerektirir

Bir sınıfın, doğrudan devraldığı bir arabirimin tüm üyelerini uygulaması gerekir. Uygulanan bir üyenin genel erişilebilirliği olması ve sanal olarak işaretlenmesi gerekir.

## <a name="examples"></a>Örnekler

C4488, uygulanan bir üyenin ortak olmaması durumunda gerçekleşebilir. Aşağıdaki örnek C4488 oluşturur.

```cpp
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

C4488, uygulanan bir üyenin sanal olarak işaretlenmemiş olması durumunda gerçekleşebilir. Aşağıdaki örnek C4488 oluşturur.

```cpp
// C4488_b.cpp
// compile with: /clr /c /W1 /WX
interface struct MyI {
   void f1();
};

ref struct B : MyI { void f1() {} };   // C4488
ref struct C : MyI { virtual void f1() {} };   // OK
```
