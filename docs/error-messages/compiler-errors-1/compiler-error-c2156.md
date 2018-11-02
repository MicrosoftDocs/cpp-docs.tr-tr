---
title: Derleyici Hatası C2156
ms.date: 11/04/2016
f1_keywords:
- C2156
helpviewer_keywords:
- C2156
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
ms.openlocfilehash: e2637a54249c37f3872d87959f2cf6d7bf73481e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532580"
---
# <a name="compiler-error-c2156"></a>Derleyici Hatası C2156

pragma işlevin dışında olmalıdır

(Bir işlev gövdesinin dışında) bir genel düzeyde belirtilmelidir bir pragma, içinde bir işlevdir.

Aşağıdaki örnek, C2156 oluşturur:

```
// C2156.cpp
#pragma optimize( "l", on )   // OK
int main() {
   #pragma optimize( "l", on )   // C2156
}
```