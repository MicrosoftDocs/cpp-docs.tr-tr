---
title: Derleyici hatası C2061
ms.date: 11/04/2016
f1_keywords:
- C2061
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
ms.openlocfilehash: 1e1b13960c84d4e03c6316c451c690f8b5a6236e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212871"
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
