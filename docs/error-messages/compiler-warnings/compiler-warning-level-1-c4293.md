---
title: Derleyici Uyarısı (düzey 1) C4293
ms.date: 11/04/2016
f1_keywords:
- C4293
helpviewer_keywords:
- C4293
ms.assetid: babecd96-eb51-41a5-9835-462c7a46dbad
ms.openlocfilehash: 03520e2018efd611985c0eeca8bb2cac259ff3cf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384224"
---
# <a name="compiler-warning-level-1-c4293"></a>Derleyici Uyarısı (düzey 1) C4293

'operator': kaydırma sayısı negatif veya çok büyük; tanımsız davranış

Kaydırma sayısı negatif veya çok büyük ise, sonuçta elde edilen görüntü davranışı tanımsızdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4293 oluşturur:

```
// C4293.cpp
// compile with: /c /W1
unsigned __int64 combine (unsigned lo, unsigned hi) {

   return (hi << 32) | lo;   // C4293

   // try the following line instead
   // return ( (unsigned __int64)hi << 32) | lo;
}
```