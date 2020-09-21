---
title: Derleyici hatası C3465
ms.date: 11/04/2016
f1_keywords:
- C3465
helpviewer_keywords:
- C3465
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
ms.openlocfilehash: 56eeac18d5b8efc32501bf54e2de3aa216e05a13
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742027"
---
# <a name="compiler-error-c3465"></a>Derleyici hatası C3465

' Type ' türünü kullanmak için ' Assembly ' derlemesine başvurmanız gerekir

İstemciyi yeniden derleyene kadar tür iletimi bir istemci uygulaması için çalışır. Yeniden derlemenizin ardından, istemci uygulamanızda kullanılan bir türün tanımını içeren her derleme için bir başvuruya ihtiyacınız olacaktır.

Daha fazla bilgi için bkz. [tür iletme (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, bir türün yeni konumunu içeren bir derleme oluşturur.

```cpp
// C3465.cpp
// compile with: /clr /LD
public ref class R {
public:
   ref class N {};
};
```

Aşağıdaki örnek, türünün tanımını içermesi için kullanılan bir derleme oluşturur, ancak artık tür için iletme sözdizimini içerir.

```cpp
// C3465_b.cpp
// compile with: /clr /LD
#using "C3465.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

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
