---
title: Derleyici Hatası C3136
ms.date: 10/03/2018
f1_keywords:
- C3136
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
ms.openlocfilehash: e32ffca067c3b25120301527e7a708d53001d541
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376256"
---
# <a name="compiler-error-c3136"></a>Derleyici Hatası C3136

'interface': bir COM arabirimi yalnızca başka bir COM arabiriminden devralabilir, 'interface' bir COM arabirimi değil

İçin uygulanan bir arabirim bir [arabirimi özniteliği](../../windows/attributes/interface-attributes.md) bir COM arabirimi değil arabiriminden devralır. Devraldığı sonuçta bir COM arabirimi `IUnknown`. Bir arabirim özniteliği tarafından öncesinde herhangi bir arabirim bir COM arabirimidir.

Aşağıdaki örnek, C3136 oluşturur:

```
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