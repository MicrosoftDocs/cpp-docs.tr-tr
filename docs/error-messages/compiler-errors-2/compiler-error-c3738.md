---
title: Derleyici Hatası C3738 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3738
dev_langs:
- C++
helpviewer_keywords:
- C3738
ms.assetid: dd3ee011-e204-4264-bf3a-da32c4ef7038
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07a71ae25f62d50ec52860e61e195f1c19f78030
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096567"
---
# <a name="compiler-error-c3738"></a>Derleyici Hatası C3738

'calling_convention': açık örnek oluşturma çağırma kuralı örneği oluşturulan şablonla eşleşmelidir

Çağırma kuralı açıkça örneklemesi belirtmeyin önerilir. Çağırma kuralları, ancak, gerekirse eşleşmelidir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3738 oluşturur.

```
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