---
title: Derleyici Hatası C3886
ms.date: 11/04/2016
f1_keywords:
- C3886
helpviewer_keywords:
- C3886
ms.assetid: 485f6c12-cc1b-4146-9034-409a0a5e615e
ms.openlocfilehash: 68ed8d6cf208ae2a53e196e7b430eae1f8fe3ca0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471805"
---
# <a name="compiler-error-c3886"></a>Derleyici Hatası C3886

'var': sabit değerli veri üyesi başlatılmalıdır

A [değişmez değer](../../windows/literal-cpp-component-extensions.md) declaraed olduğunda değişkeni'nin başlatılması gerekir.

Aşağıdaki örnek, C3886 oluşturur:

```
// C3886.cpp
// compile with: /clr /c
ref struct Y1 {
   literal int staticConst;   // C3886
   literal int staticConst2 = 0;   // OK
};
```