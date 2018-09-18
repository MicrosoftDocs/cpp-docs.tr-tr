---
title: Derleyici Hatası C2362 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2362
dev_langs:
- C++
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f78b850f95614255fed372570742a0f88a9e30e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035987"
---
# <a name="compiler-error-c2362"></a>Derleyici Hatası C2362

'identifier' öğesinin başlatılması 'goto etiketle' atlandı

İle derlerken [/Za](../../build/reference/za-ze-disable-language-extensions.md), etikete atladıktan engeller tanımlayıcı başlatılmış.

Bildirimi olmayan girilen bir bloğu içinde alınmış sürece bir bildirimi bir başlatıcıya sahip son atlama olamaz veya değişken zaten başlatıldı.

Aşağıdaki örnek, C2326 oluşturur:

```
// C2362.cpp
// compile with: /Za
int main() {
   goto label1;
   int i = 1;      // C2362, initialization skipped
label1:;
}
```

Olası çözüm:

```
// C2362b.cpp
// compile with: /Za
int main() {
   goto label1;
   {
      int j = 1;   // OK, this block is never entered
   }
label1:;
}
```