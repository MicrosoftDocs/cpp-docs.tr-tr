---
title: Derleyici hatası C2179
ms.date: 11/04/2016
f1_keywords:
- C2179
helpviewer_keywords:
- C2179
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
ms.openlocfilehash: 5b9b5382ab934f8d870e58189a447775a1e9a415
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737172"
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
