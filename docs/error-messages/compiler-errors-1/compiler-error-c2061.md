---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2061'
title: Derleyici hatası C2061
ms.date: 11/04/2016
f1_keywords:
- C2061
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
ms.openlocfilehash: e857f4c4de90fadecdd7b7062306391b4222bcf4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328730"
---
# <a name="compiler-error-c2061"></a>Derleyici hatası C2061

sözdizimi hatası: tanımlayıcı ' tanımlayıcı '

Derleyici, beklenmediği bir tanımlayıcı buldu. ' `identifier` In kullanılmadan önce bildirildiği emin olun.

Bir başlatıcı parantez içine alınmış olabilir. Bu sorundan kaçınmak için, bildirimcisini parantez içine alın veya bir yapın **`typedef`** .

Bu hata, derleyici bir sınıf şablonu bağımsız değişkeni olarak bir ifade algıladığında de oluşabilir; derleyiciye bir tür olduğunu bildirmek için [TypeName](../../cpp/typename.md) kullanın.

Aşağıdaki örnek C2061 oluşturur:

```cpp
// C2061.cpp
// compile with: /c
template < A a >   // C2061
// try the following line instead
// template < typename b >
class c{};
```

[TypeId](../../extensions/typeid-cpp-component-extensions.md)öğesine bir örnek adı geçirirseniz, C2061 oluşabilir:

```cpp
// C2061b.cpp
// compile with: /clr
ref struct G {
   int i;
};

int main() {
   G ^ pG = gcnew G;
   System::Type ^ pType = typeid<pG>;   // C2061
   System::Type ^ pType2 = typeid<G>;   // OK
}
```
