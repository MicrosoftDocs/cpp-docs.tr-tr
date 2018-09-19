---
title: Derleyici Uyarısı (düzey 4) C4681 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4681
dev_langs:
- C++
helpviewer_keywords:
- C4681
ms.assetid: a4e6d85f-3e21-4b45-a551-c23d3c554d3f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c96d019215c1e91707cc73c65a7a40b0ae4b21a5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114494"
---
# <a name="compiler-warning-level-4-c4681"></a>Derleyici Uyarısı (düzey 4) C4681

'class': coclass olay kaynağı olan varsayılan bir arabirim belirtmiyor

A [kaynak](../../windows/source-cpp.md) arabirimi, bir sınıf için belirtilmedi.

Aşağıdaki örnek, C4681 oluşturur:

```
// C4681.cpp
// compile with: /W4 /c
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[module(name="test")];

[dual, uuid("00000000-0000-0000-0000-000000000000")]
__interface IEvent { [id(3)] HRESULT myEvent(); };

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface ISource { HRESULT Fire(); };

[ coclass,
  source(IEvent),
  default(ISource),
  // Uncomment the following line to resolve.
  // default(IEvent),
  uuid("00000000-0000-0000-0000-000000000002")
]
struct CSource : ISource {   // C4681
   HRESULT Fire() { return 0; }
};
```