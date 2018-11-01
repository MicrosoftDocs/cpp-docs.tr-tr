---
title: Derleyici Hatası C2159
ms.date: 11/04/2016
f1_keywords:
- C2159
helpviewer_keywords:
- C2159
ms.assetid: 925a2cbd-43c9-45ee-a373-84004350b380
ms.openlocfilehash: fd845fffe9778e51af7db77144607233ed9ddefd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575116"
---
# <a name="compiler-error-c2159"></a>Derleyici Hatası C2159

Belirtilen birden fazla depolama sınıfı

Bir bildirimi birden fazla depolama sınıfı içerir.

Aşağıdaki örnek, C2159 oluşturur:

```
// C2159.cpp
// compile with: /c
static int i;   // OK
extern static int i;   // C2159
```