---
title: Derleyici Uyarısı (düzey 1) C4393
ms.date: 11/04/2016
f1_keywords:
- C4393
helpviewer_keywords:
- C4393
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
ms.openlocfilehash: 4226c8ecd41e890d70fa5741decae605d45b620f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777048"
---
# <a name="compiler-warning-level-1-c4393"></a>Derleyici Uyarısı (düzey 1) C4393

'var': const; sabit değerli veri üyesi üzerinde etkiye sahip değildir yoksayıldı

A [değişmez değer](../../extensions/literal-cpp-component-extensions.md) veri üyesi de const olarak belirtildi.  Sabit değerli veri üyesi const gelir olduğundan, eklemek const bildirimine gerekmez.

Aşağıdaki örnek, C4393 oluşturur:

```
// C4393.cpp
// compile with: /clr /W1 /c
ref struct Y1 {
   literal const int staticConst = 10;   // C4393
   literal int staticConst2 = 10;   // OK
};
```