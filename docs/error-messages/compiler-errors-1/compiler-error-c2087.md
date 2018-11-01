---
title: Derleyici Hatası C2087
ms.date: 11/04/2016
f1_keywords:
- C2087
helpviewer_keywords:
- C2087
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
ms.openlocfilehash: 11d5a0a86ba399e28a641fa490f19be020db2d9d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527432"
---
# <a name="compiler-error-c2087"></a>Derleyici Hatası C2087

'identifier': indis eksik

Birden çok alt simgeye sahip bir dizi tanımı birden daha yüksek bir boyut için alt simge bir değer eksik.

Aşağıdaki örnek, C2087 oluşturur:

```
// C2087.cpp
int main() {
   char a[10][];   // C2087
}
```

Olası çözüm:

```
// C2087b.cpp
int main() {
   char b[4][5];
}
```