---
title: Derleyici Uyarısı (düzey 1) C4488
ms.date: 11/04/2016
f1_keywords:
- C4488
helpviewer_keywords:
- C4488
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
ms.openlocfilehash: b83845f0ed0efeee6485780c7e4f828e40473e9e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186705"
---
# <a name="compiler-warning-level-1-c4488"></a>Derleyici Uyarısı (düzey 1) C4488

' function ': ' interface_method ' arabirim yöntemini uygulamak için ' anahtar sözcüğü ' anahtar sözcüğünü gerektirir

Bir sınıfın, doğrudan devraldığı bir arabirimin tüm üyelerini uygulaması gerekir. Uygulanan bir üyenin genel erişilebilirliği olması ve sanal olarak işaretlenmesi gerekir.

## <a name="example"></a>Örnek

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

## <a name="example"></a>Örnek

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
