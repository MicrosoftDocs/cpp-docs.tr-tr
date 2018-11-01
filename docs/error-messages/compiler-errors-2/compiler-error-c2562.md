---
title: Derleyici Hatası C2562
ms.date: 11/04/2016
f1_keywords:
- C2562
helpviewer_keywords:
- C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
ms.openlocfilehash: c665c4ed82fefaf0ee724defb8c205f86fc06dd0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435316"
---
# <a name="compiler-error-c2562"></a>Derleyici Hatası C2562

'identifier': 'void' işlev değer döndürüyor

Olarak bildirilen işlev `void` ancak bir değer döndürür.

Bu hata bir hatalı işlev prototipi tarafından neden olabilir.

Dönüş türü işlev bildiriminin belirtirseniz, bu hata sabit olamaz.

Aşağıdaki örnek, C2562 oluşturur:

```
// C2562.cpp
// compile with: /c
void testfunc() {
   int i;
   return i;   // C2562 delete the return to resolve
}
```