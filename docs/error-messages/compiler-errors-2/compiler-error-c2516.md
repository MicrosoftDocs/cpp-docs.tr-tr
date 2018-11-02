---
title: Derleyici Hatası C2516
ms.date: 11/04/2016
f1_keywords:
- C2516
helpviewer_keywords:
- C2516
ms.assetid: cd3accc1-0179-4a13-9587-616908c4ad1d
ms.openlocfilehash: 2114ad048c2061b81f223c86536f23737bdf43fb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540068"
---
# <a name="compiler-error-c2516"></a>Derleyici Hatası C2516

'name': geçerli bir taban sınıf değil

Sınıfı tarafından tanımlanan bir tür adı türetilmiş bir `typedef` deyimi.

Aşağıdaki örnek, C2516 oluşturur:

```
// C2516.cpp
typedef unsigned long ulong;
class C : public ulong {}; // C2516
```