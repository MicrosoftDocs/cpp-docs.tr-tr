---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3887'
title: Derleyici hatası C3887
ms.date: 11/04/2016
f1_keywords:
- C3887
helpviewer_keywords:
- C3887
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
ms.openlocfilehash: 8c80a1ff54f56e111934ebc370fee28f011bd37b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274352"
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
