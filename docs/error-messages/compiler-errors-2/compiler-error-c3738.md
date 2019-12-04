---
title: Derleyici hatası C3738
ms.date: 11/04/2016
f1_keywords:
- C3738
helpviewer_keywords:
- C3738
ms.assetid: dd3ee011-e204-4264-bf3a-da32c4ef7038
ms.openlocfilehash: ffefa0eff23e11412573b8062fa15bb5679923e7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752775"
---
# <a name="compiler-error-c3738"></a>Derleyici hatası C3738

' calling_convention ': açık örnek oluşturmanın çağırma kuralı, örneği oluşturulan şablonla eşleşmelidir

Açık bir örnek oluşturmada çağırma kuralı belirtmemektir. Ancak,, çağırma kurallarının eşleşmesi gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3738 oluşturur.

```cpp
// C3738.cpp
// compile with: /clr
// processor: x86
#include <stdio.h>
template< class T >
void f ( T arg ) {   // by default calling convention is __cdecl
   printf ( "f: %s\n", __FUNCSIG__ );
}

template
void __stdcall f< int > ( int arg );   // C3738
// try the following line instead
// void f< int > ( int arg );

int main () {
   f(1);
   f< int > ( 1 );
}
```
