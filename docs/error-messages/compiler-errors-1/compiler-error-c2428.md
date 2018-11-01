---
title: Derleyici Hatası C2428
ms.date: 11/04/2016
f1_keywords:
- C2428
helpviewer_keywords:
- C2428
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
ms.openlocfilehash: 299a4e899a41bf47eec5eaf5b54d2307e557078e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614675"
---
# <a name="compiler-error-c2428"></a>Derleyici Hatası C2428

'operation': 'bool' türü işlenen üzerinde izin verilmiyor

Azaltma işleci türündeki nesnelere uygulayamazsınız `bool`.

Aşağıdaki örnek, C2428 oluşturur:

```
// C2428.cpp
void g(bool fFlag) {
   --fFlag;   // C2428
   fFlag--;   // C2428
}
```