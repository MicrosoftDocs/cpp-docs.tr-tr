---
title: Derleyici Uyarısı (düzey 1) C4096
ms.date: 11/04/2016
f1_keywords:
- C4096
helpviewer_keywords:
- C4096
ms.assetid: abf3cca2-2f21-45d8-b025-6b513b00681e
ms.openlocfilehash: 287465e9a3f5681f459f0823a4409b0906309a55
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436556"
---
# <a name="compiler-warning-level-1-c4096"></a>Derleyici Uyarısı (düzey 1) C4096

'bir': arabirim bir COM arabirimi değil IDL için yayılan değil

Bir COM arabirimi olarak hedeflenen bir arabirim tanımı, bir COM arabirimi olarak tanımlı değil ve bu nedenle IDL dosyasına yayılan değil.

Bkz: [arabirim öznitelikleri](../../windows/attributes/interface-attributes.md) için bir arabirim bir COM arabirimi olduğunu belirten bir liste öznitelikleri.

Aşağıdaki örnek, C4096 oluşturur:

```
// C4096.cpp
// compile with: /W1 /LD
#include "windows.h"
[module(name="xx")];

// [object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[coclass, uuid("00000000-0000-0000-0000-000000000002")]
struct b : a
{
};   // C4096, remove coclass or uncomment object
```