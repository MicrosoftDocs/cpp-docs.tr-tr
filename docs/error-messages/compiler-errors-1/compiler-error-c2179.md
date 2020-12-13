---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2179'
title: Derleyici hatası C2179
ms.date: 11/04/2016
f1_keywords:
- C2179
helpviewer_keywords:
- C2179
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
ms.openlocfilehash: 17ddc839161f36efc668bb52504e2434ec82f995
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335220"
---
# <a name="compiler-error-c2179"></a>Derleyici hatası C2179

' Type ': öznitelik bağımsız değişkeni tür parametreleri kullanamaz

Çalışma zamanında genel bir tür parametresi çözüldü. Ancak, bir öznitelik parametresi derleme zamanında çözümlenmelidir. Bu nedenle, bir özniteliğe bağımsız değişken olarak genel bir tür parametresi kullanamazsınız.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2179 oluşturur.

```cpp
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
