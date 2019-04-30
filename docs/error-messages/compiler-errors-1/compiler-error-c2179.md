---
title: Derleyici Hatası C2179
ms.date: 11/04/2016
f1_keywords:
- C2179
helpviewer_keywords:
- C2179
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
ms.openlocfilehash: 4a8abd8d862d4d6b08b1d0efd1d47d0413b60a81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385998"
---
# <a name="compiler-error-c2179"></a>Derleyici Hatası C2179

'type': öznitelik bağımsız değişkeni tür parametreleri kullanamaz

Genel tür parametresi, çalışma zamanında çözülür. Ancak, bir öznitelik parametresi, derleme zamanında çözümlenmelidir. Bu nedenle, bir öznitelik bağımsız değişkeni olarak bir genel tür parametresi kullanılamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2179 oluşturur.

```
// C2179.cpp
// compile with: /clr
using namespace System;

public ref struct Attr : Attribute {
   Attr(Type ^ a) {
      x = a;
   }

   Type ^ x;
};

ref struct G {};

generic<typename T>
public ref class Z {
public:
   Type ^ d;
   [Attr(T::typeid)]   // C2179
   // try the following line instead
   // [Attr(G::typeid)]
   T t;
};
```