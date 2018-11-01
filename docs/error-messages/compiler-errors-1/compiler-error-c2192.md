---
title: Derleyici Hatası C2192
ms.date: 11/04/2016
f1_keywords:
- C2192
helpviewer_keywords:
- C2192
ms.assetid: a147197e-e72d-4620-939b-f9e08d7c7c12
ms.openlocfilehash: 3285221089c2a1ed61b03572ed8915ebfbb00e48
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444258"
---
# <a name="compiler-error-c2192"></a>Derleyici Hatası C2192

parametresi, 'number', bildirimi farklı

C işlevi, ikinci kez farklı parametre listesiyle bildirildi. C, aşırı yüklenmiş işlevler desteklemez.

Aşağıdaki örnek, C2192 oluşturur:

```
// C2192.c
// compile with: /Za /c
void func( float, int );
void func( int, float );   // C2192, different parameter list
void func2( int, float );   // OK
```