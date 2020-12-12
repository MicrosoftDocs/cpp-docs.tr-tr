---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3465'
title: Derleyici hatası C3465
ms.date: 11/04/2016
f1_keywords:
- C3465
helpviewer_keywords:
- C3465
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
ms.openlocfilehash: ab5d55b5e21241eb2bbab00524f3c81baaace88f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113460"
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
