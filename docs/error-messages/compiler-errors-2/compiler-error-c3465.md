---
title: Derleyici hatası C3465
ms.date: 11/04/2016
f1_keywords:
- C3465
helpviewer_keywords:
- C3465
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
ms.openlocfilehash: 1d82d367c5b77f54548403b7b142aa740919b6c2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756571"
---
# <a name="compiler-error-c3465"></a>Derleyici hatası C3465

' Type ' türünü kullanmak için ' Assembly ' derlemesine başvurmanız gerekir

İstemciyi yeniden derleyene kadar tür iletimi bir istemci uygulaması için çalışır. Yeniden derlemenizin ardından, istemci uygulamanızda kullanılan bir türün tanımını içeren her derleme için bir başvuruya ihtiyacınız olacaktır.

Daha fazla bilgi için bkz. [tür iletmeC++(/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir türün yeni konumunu içeren bir derleme oluşturur.

```cpp
// C3465.cpp
// compile with: /clr /LD
public ref class R {
public:
   ref class N {};
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, türünün tanımını içermesi için kullanılan bir derleme oluşturur, ancak artık tür için iletme sözdizimini içerir.

```cpp
// C3465_b.cpp
// compile with: /clr /LD
#using "C3465.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

## <a name="example"></a>Örnek

Aşağıdaki örnek C3465 oluşturur.

```cpp
// C3465_c.cpp
// compile with: /clr
// C3465 expected
#using "C3465_b.dll"
// Uncomment the following line to resolve.
// #using "C3465.dll"

int main() {
   R^ r = gcnew R();
}
```
