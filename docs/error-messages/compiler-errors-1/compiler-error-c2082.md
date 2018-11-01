---
title: Derleyici Hatası C2082
ms.date: 11/04/2016
f1_keywords:
- C2082
helpviewer_keywords:
- C2082
ms.assetid: 87a6d442-157c-46e8-9bff-8388f8338ae0
ms.openlocfilehash: 8bfb54dc91ef9132e3930e2c0799070f80f5cd0f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577261"
---
# <a name="compiler-error-c2082"></a>Derleyici Hatası C2082

'identifier' biçimsel parametresinin yeniden tanımlanması

Bir işlevin biçimsel parametresi, işlev gövdesinde'yeniden tanımlanıyor. Hatayı gidermek için tekrar tanımlama orijinaliyle kaldırın.

Aşağıdaki örnek, C2082 oluşturur:

```
// C2082.cpp
void func(int i) {
   int i;   // C2082
   int ii;   // OK
}
```