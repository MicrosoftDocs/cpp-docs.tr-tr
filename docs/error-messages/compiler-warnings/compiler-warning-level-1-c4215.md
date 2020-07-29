---
title: Derleyici Uyarısı (düzey 1) C4215
ms.date: 11/04/2016
f1_keywords:
- C4215
helpviewer_keywords:
- C4215
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
ms.openlocfilehash: aeab5a90647015a8848d7c2af62f7d7fc6932900
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223284"
---
# <a name="compiler-warning-level-1-c4215"></a>Derleyici Uyarısı (düzey 1) C4215

Standart olmayan uzantı kullanıldı: uzun float

Varsayılan Microsoft uzantıları (/Ze), **uzun float** olarak değerlendirilir **`double`** . ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) değil. **`double`** Uyumluluğu korumak için kullanın.

Aşağıdaki örnek C4215 oluşturur:

```cpp
// C4215.cpp
// compile with: /W1 /LD
long float a;   // C4215

// use the line below to resolve the warning
// double a;
```
