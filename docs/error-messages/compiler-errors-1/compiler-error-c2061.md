---
title: Derleyici Hatası C2061
ms.date: 11/04/2016
f1_keywords:
- C2061
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
ms.openlocfilehash: 0bd1e770e38fcb85164bfa205470ac55a12e1c87
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466202"
---
# <a name="compiler-error-c2061"></a>Derleyici Hatası C2061

sözdizimi hatası: 'identifier' tanımlayıcısı

Derleyici, beklenirken değildi tanımlayıcı bulunamadı. Emin olun `identifier` kullanmadan önce bildirilir.

Bir başlatıcı parantez ile kapatılan. Bu sorunu önlemek için bildirimci parantez içine veya hale bir `typedef`.

Derleyici bir sınıf şablonu bağımsız değişkeni olarak bir ifade algıladığında bu hatayı da neden olmuş olabilir; kullanma [typename](../../cpp/typename.md) bir türü olduğundan derleyici söylemek için.

Aşağıdaki örnek, C2061 oluşturur:

```
// C2061.cpp
// compile with: /c
template < A a >   // C2061
// try the following line instead
// template < typename b >
class c{};
```

Bir örnek adı için geçirirseniz C2061 oluşabilir [TypeID](../../windows/typeid-cpp-component-extensions.md):

```
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