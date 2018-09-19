---
title: Derleyici Hatası C2087 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2087
dev_langs:
- C++
helpviewer_keywords:
- C2087
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38b6ce6c0b2435143ece8d431271c97a3f48a2b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101962"
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