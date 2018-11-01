---
title: Derleyici Hatası C2213
ms.date: 11/04/2016
f1_keywords:
- C2213
helpviewer_keywords:
- C2213
ms.assetid: ff012278-7f3b-4d49-aaed-2349756f6225
ms.openlocfilehash: 125529aa23d43d9acd63652f73f636fee567f90a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50433453"
---
# <a name="compiler-error-c2213"></a>Derleyici Hatası C2213

'değiştiricisi': __based için geçersiz bağımsız değişken

Bağımsız değişken değiştirme `__based` geçersiz.

Aşağıdaki örnek, C2213 oluşturur:

```
// C2213.cpp
// compile with: /c
int i;
int *j;
char __based(i) *p;   // C2213
char __based(j) *p2;   // OK
```