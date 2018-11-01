---
title: Derleyici Hatası C2386
ms.date: 11/04/2016
f1_keywords:
- C2386
helpviewer_keywords:
- C2386
ms.assetid: aaaa1284-34a0-4da2-8547-9fcbb559dae0
ms.openlocfilehash: a75ccd9824106f2b954cd090a0e00ab11786d243
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667668"
---
# <a name="compiler-error-c2386"></a>Derleyici Hatası C2386

'symbol': Bu ada sahip bir simge geçerli kapsamda zaten var.

Ad alanı diğer adı oluşturmak denedik ancak önceden seçtiğiniz adı yok.

Aşağıdaki örnek, C2386 oluşturur:

```
// C2386.cpp
namespace A {
   int k;
}

int i;
namespace i = A;   // C2386, i already exists
```