---
title: Derleyici Hatası C2395
ms.date: 11/04/2016
f1_keywords:
- C2395
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
ms.openlocfilehash: dd3bd922e2bfa61da2da87d368bb4b28237161f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599850"
---
# <a name="compiler-error-c2395"></a>Derleyici Hatası C2395

' your_type::operator'op'': CLR veya WinRT işleci geçerli değil. En az bir parametre aşağıdaki türlerde olmalıdır: 'T', 'T %', 'T &', 'T ^', 'T ^ %', 'T ^ &', burada T = 'your_type'

Bir Windows çalışma zamanı veya yönetilen türü bir işleç türü işleç dönüş değerinin türü ile aynı olan en az bir parametre yok.

Aşağıdaki örnek, C2395 oluşturur ve bu sorunun nasıl gösterir:

```
// C2395.cpp
// compile with: /clr /c
value struct V {
   static V operator *(int i, char c);   // C2395

   // OK
   static V operator *(V v, char c);
   // or
   static V operator *(int i, V& rv);
};
```