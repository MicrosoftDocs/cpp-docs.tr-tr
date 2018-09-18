---
title: Derleyici Hatası C2063 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2063
dev_langs:
- C++
helpviewer_keywords:
- C2063
ms.assetid: 0a90c18f-4029-416a-9128-e8713b53e6f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3705192ba73faba88c63de5f4361449248e712e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100415"
---
# <a name="compiler-error-c2063"></a>Derleyici Hatası C2063

'identifier': bir işlev değil

Tanımlayıcı bir işlev olarak kullanılan, ancak bir işlev olarak yapılmadı.

Aşağıdaki örnek, C2063 oluşturur:

```
// C2063.c
int main() {
   int i, j;
   j = i();    // C2063, i is not a function
}
```

Olası çözüm:

```
// C2063b.c
int i() { return 0;}
int main() {
   int j;
   j = i();
}
```