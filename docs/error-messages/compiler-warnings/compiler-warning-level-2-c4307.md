---
title: Derleyici Uyarısı (Düzey 2) C4307
ms.date: 11/04/2016
f1_keywords:
- C4307
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
ms.openlocfilehash: e9ad30f60260893130beed921aab811c894868cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528160"
---
# <a name="compiler-warning-level-2-c4307"></a>Derleyici Uyarısı (Düzey 2) C4307

'operator': tamsayı sabiti taştı

İşleci, bir tamsayı sabiti için ayrılan alanı taşma sonuçlanır bir ifadede kullanılır. Daha büyük bir tür için bir sabit kullanmanız gerekebilir. A **signed int** küçük bir değeri tutan bir `unsigned int` çünkü **signed int** oturum temsil eden bir bit kullanır.

Aşağıdaki örnek, C4307 oluşturur:

```
// C4307.cpp
// compile with: /W2
int i = 2000000000 + 2000000000;   // C4307
int j = (unsigned)2000000000 + 2000000000;   // OK

int main()
{
}
```