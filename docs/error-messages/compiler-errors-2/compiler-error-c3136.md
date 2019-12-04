---
title: Derleyici hatası C3136
ms.date: 10/03/2018
f1_keywords:
- C3136
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
ms.openlocfilehash: 75862f3b80d617b607a7b3e735cb3e16e9a40bb7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757390"
---
# <a name="compiler-error-c3136"></a>Derleyici hatası C3136

' interface ': COM arabirimi yalnızca başka bir COM arabiriminden devralınabilir, ' Interface ' bir COM arabirimi değil

Bir [arabirim özniteliğini](../../windows/attributes/interface-attributes.md) uyguladığınız ARABIRIM, com arabirimi olmayan bir arabirimden devralınır. Bir COM arabirimi sonunda `IUnknown`devralır. Önünde bir arabirim özniteliği olan herhangi bir arabirim bir COM arabirimidir.

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
