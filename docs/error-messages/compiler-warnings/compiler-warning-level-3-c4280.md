---
title: Derleyici Uyarısı (Düzey 3) C4280 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4280
dev_langs:
- C++
helpviewer_keywords:
- C4280
ms.assetid: 153fb639-3ee1-4fee-baf9-71420abcf3f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa1446e6725ecbb990e38ede33071afddb54065f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118329"
---
# <a name="compiler-warning-level-3-c4280"></a>Derleyici Uyarısı (Düzey 3) C4280

'operator ->' kendi kendine özniyeleniyordu türü aracılığıyla 'type'

Kodunuzun yanlış sağlar **-> işleci** kendisini çağırmak için.

Aşağıdaki örnek, C4280 oluşturur:

```
// C4280.cpp
// compile with: /W3 /WX
struct A
{
   int z;
   A& operator ->();
};

void f(A y)
{
   int i = y->z; // C4280
}
```