---
title: Derleyici Hatası C3887
ms.date: 11/04/2016
f1_keywords:
- C3887
helpviewer_keywords:
- C3887
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
ms.openlocfilehash: e41ea1dbe1f2bd47f9b557d502ec95bcecb1e2a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428269"
---
# <a name="compiler-error-c3887"></a>Derleyici Hatası C3887

'var': sabit değerli veri üyesi başlatıcısı sabit ifade olmalıdır

A [değişmez değer](../../windows/literal-cpp-component-extensions.md) veri üyesi ile sabit bir ifade yalnızca başlatılabilir.

Aşağıdaki örnek, C3887 oluşturur:

```
// C3887.cpp
// compile with: /clr
ref struct Y1 {
   static int i = 9;
   literal
   int staticConst = i;   // C3887
};
```

Olası çözüm:

```
// C3887b.cpp
// compile with: /clr /c
ref struct Y1 {
   literal
   int staticConst = 9;
};
```