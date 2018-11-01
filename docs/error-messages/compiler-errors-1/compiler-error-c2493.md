---
title: Derleyici Hatası C2493
ms.date: 11/04/2016
f1_keywords:
- C2493
helpviewer_keywords:
- C2493
ms.assetid: 68316cd5-682b-49c3-b6ea-23c4e5d296cf
ms.openlocfilehash: d5e64b2586803f7463582710721d2cb5c0eac200
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443010"
---
# <a name="compiler-error-c2493"></a>Derleyici Hatası C2493

Geçersiz __based biçimi

A `__based` ifade işaretçiye temel alabilir.

Aşağıdaki örnek, C2493 oluşturur:

```
// C2493.cpp
// compile with: /c
char mybase;
int __based(mybase) ptr;   // C2493

// OK
char * mybase;
int __based(mybase) * ptr;
```