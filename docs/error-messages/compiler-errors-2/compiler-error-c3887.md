---
title: Derleyici hatası C3887
ms.date: 11/04/2016
f1_keywords:
- C3887
helpviewer_keywords:
- C3887
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
ms.openlocfilehash: f64b72fe5d546550c32f60a27360d8a77c8255bd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736587"
---
# <a name="compiler-error-c3887"></a>Derleyici hatası C3887

' var ': sabit değerli bir veri üyesinin başlatıcısı sabit bir ifade olmalıdır

[Sabit değerli](../../extensions/literal-cpp-component-extensions.md) bir veri üyesi yalnızca sabit bir ifade ile başlatılabilir.

Aşağıdaki örnek C3887 oluşturur:

```cpp
// C3887.cpp
// compile with: /clr
ref struct Y1 {
   static int i = 9;
   literal
   int staticConst = i;   // C3887
};
```

Olası çözüm:

```cpp
// C3887b.cpp
// compile with: /clr /c
ref struct Y1 {
   literal
   int staticConst = 9;
};
```
