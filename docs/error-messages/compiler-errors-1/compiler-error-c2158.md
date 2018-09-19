---
title: Derleyici Hatası C2158 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2158
dev_langs:
- C++
helpviewer_keywords:
- C2158
ms.assetid: 39028899-e95c-4809-8e65-6111118641ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e853e5915756b71b96e50374224b003eca412d99
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034908"
---
# <a name="compiler-error-c2158"></a>Derleyici Hatası C2158

'type': #pragma make_public yönergesi şu anda yalnızca yerel şablon olmayan türler desteklenmiyor

[Make_public](../../preprocessor/make-public.md) pragma yalnızca yerel, şablon olmayan bir türe uygulanabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2158 oluşturur.

```
// C2158.cpp
// compile with: /clr /c
ref class A {};
#pragma make_public(A)   // C2158

template< typename T >
class B {};
#pragma make_public(B)   // C2158
#pragma make_public(B<int>)   // C2158

void C () {}
#pragma make_public(C)   // C2158

class D {};
#pragma make_public(D)   // OK
```