---
title: Derleyici Uyarısı (düzey 1) C4172
ms.date: 11/04/2016
f1_keywords:
- C4172
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
ms.openlocfilehash: caa71da9182c1da1d17d87d901084d0ee9badf73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536632"
---
# <a name="compiler-warning-level-1-c4172"></a>Derleyici Uyarısı (düzey 1) C4172

yerel değişkenin veya geçici adresini döndürüyor

Bir işlev bir yerel değişken veya geçici nesnenin adresini döndürür. Bir işlev geri döndüğünde, döndürülen adresi geçerli değil. Bu nedenle yerel değişkenleri ve geçici nesneler yok edilir.

İşlevi, yerel bir nesnenin adresini döndürmeyen olacak şekilde yeniden tasarlayın.

Aşağıdaki örnek, C4172 oluşturur:

```
// C4172.cpp
// compile with: /W1 /LD
float f = 10;

const double& bar() {
// try the following line instead
// const float& bar() {
   return f;   // C4172
}
```