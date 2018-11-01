---
title: Derleyici Hatası C2806
ms.date: 11/04/2016
f1_keywords:
- C2806
helpviewer_keywords:
- C2806
ms.assetid: 7c9ff1f4-1590-4c47-991d-b1075a173b48
ms.openlocfilehash: 1d37f5d1c6e253c01ae8a3b7640fb3ee4cf12534
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490382"
---
# <a name="compiler-error-c2806"></a>Derleyici Hatası C2806

'operator işleci' çok fazla sayıda biçimsel parametre içeriyor

Aşırı yüklenmiş bir işleç çok fazla parametreye sahip.

Aşağıdaki örnek, C2806 oluşturur:

```
// C2806.cpp
// compile with: /c
class X {
public:
   X operator++ ( int, int );   // C2806 more than 1 parameter
   X operator++ ( int );   // OK
} ;
```