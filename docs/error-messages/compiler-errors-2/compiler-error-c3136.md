---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3136'
title: Derleyici hatası C3136
ms.date: 10/03/2018
f1_keywords:
- C3136
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
ms.openlocfilehash: 4203eaa1f41603075bbb8162b7156783c8f2680a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239382"
---
# <a name="compiler-error-c3136"></a>Derleyici hatası C3136

' interface ': COM arabirimi yalnızca başka bir COM arabiriminden devralınabilir, ' Interface ' bir COM arabirimi değil

Bir [arabirim özniteliğini](../../windows/attributes/interface-attributes.md) uyguladığınız ARABIRIM, com arabirimi olmayan bir arabirimden devralınır. Sonuçta bir COM arabirimi öğesinden devralır `IUnknown` . Önünde bir arabirim özniteliği olan herhangi bir arabirim bir COM arabirimidir.

Aşağıdaki örnek C3136 oluşturur:

```cpp
// C3136.cpp
#include "unknwn.h"

__interface A   // C3136
// try the following line instead
// _interface A : IUnknown
{
   int a();
};

[object]
__interface B : A
{
   int aa();
};
```
