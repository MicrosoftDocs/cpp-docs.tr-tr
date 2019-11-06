---
title: Derleyici Uyarısı (düzey 1) C4215
ms.date: 11/04/2016
f1_keywords:
- C4215
helpviewer_keywords:
- C4215
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
ms.openlocfilehash: 91be04f927c63ccbb0668bbe70cbd7c5813f8dfc
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627341"
---
# <a name="compiler-warning-level-1-c4215"></a>Derleyici Uyarısı (düzey 1) C4215

Standart olmayan uzantı kullanıldı: uzun float

Varsayılan Microsoft uzantıları (/Ze), **uzun float** değerini **Double**olarak işler. ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) değil. Uyumluluğu sürdürmek için **Double** kullanın.

Aşağıdaki örnek C4215 oluşturur:

```cpp
// C4215.cpp
// compile with: /W1 /LD
long float a;   // C4215

// use the line below to resolve the warning
// double a;
```