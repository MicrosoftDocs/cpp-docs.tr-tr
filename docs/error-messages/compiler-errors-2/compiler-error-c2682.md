---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2682'
title: Derleyici hatası C2682
ms.date: 11/04/2016
f1_keywords:
- C2682
helpviewer_keywords:
- C2682
ms.assetid: 30c6a7c4-f5f7-4fe8-81a8-c48938521ab4
ms.openlocfilehash: 962debb0227347abe97e290db724fdb227212914
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177438"
---
# <a name="compiler-error-c2682"></a>Derleyici hatası C2682

' type1 ' değerinden ' type2 ' türüne dönüştürmek için casting_operator kullanılamaz

Atama işleci uyumsuz türler arasında dönüştürmeye çalıştı. Örneğin, bir işaretçiyi bir başvuruya dönüştürmek için [dynamic_cast](../../cpp/dynamic-cast-operator.md) işlecini kullanamazsınız. **`dynamic_cast`** İşleç, niteleyicileri dönüştürmek için kullanılamaz. Türlerindeki tüm niteleyiciler eşleşmelidir.

**`const_cast`**, Veya gibi öznitelikleri kaldırmak için işlecini kullanabilirsiniz **`const`** **`volatile`** **`__unaligned`** .

Aşağıdaki örnek C2682 oluşturur:

```cpp
// C2682.cpp
class A { virtual void f(); };
class B: public A {};

void g(A* pa) {
    B& rb = dynamic_cast<B&>(pa); // C2682
}
```

Aşağıdaki örnek C2682 oluşturur:

```cpp
// C2682b.cpp
// compile with: /clr
ref struct R{};
ref struct RR : public R{};
ref struct H {
   RR^ r ;
   short s;
   int i;
};

int main() {
   H^ h = gcnew H();
   interior_ptr<int>lr = &(h->i);
   interior_ptr<short>ssr = safe_cast<interior_ptr<short> >(lr);   // C2682
   interior_ptr<short>ssr = reinterpret_cast<interior_ptr<short> >(lr);   // OK
}
```
