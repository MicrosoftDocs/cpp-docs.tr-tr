---
title: Derleyici Hatası C3136 | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3136
dev_langs:
- C++
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 082a89b69092a8320f6bb4b930d01a7fd2de10c8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788389"
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