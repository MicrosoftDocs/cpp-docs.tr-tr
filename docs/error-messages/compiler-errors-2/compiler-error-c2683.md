---
title: Derleyici hatası C2683
ms.date: 11/04/2016
f1_keywords:
- C2683
helpviewer_keywords:
- C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
ms.openlocfilehash: cd629b093bdc3992a8ea69f498b1e1cdab1b8826
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214639"
---
# <a name="compiler-error-c2683"></a>Derleyici hatası C2683

' cast ': ' Type ' polimorfik bir tür değil

Çok biçimli olmayan bir sınıftan (sanal işlevleri olmayan bir sınıf) dönüştürmek için [dynamic_cast](../../cpp/dynamic-cast-operator.md) kullanamazsınız.

[Static_cast](../../cpp/static-cast-operator.md) , çok biçimli olmayan türlerin dönüştürmeleri gerçekleştirmek için kullanabilirsiniz. Ancak, **`static_cast`** bir çalışma zamanı denetimi gerçekleştirmez.

Aşağıdaki örnek C2683 oluşturur:

```cpp
// C2683.cpp
// compile with: /c
class B { };
class D : public B { };

void f(B* pb) {
   D* pd1 = dynamic_cast<D*>(pb);  // C2683
   D* pd1 = static_cast<D*>(pb);   // OK
}
```
