---
title: Derleyici Hatası C2362
ms.date: 11/04/2016
f1_keywords:
- C2362
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
ms.openlocfilehash: 17656b2a48a3680a9269d3ca300fd4188eda6b84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661116"
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