---
title: Derleyici Uyarısı (düzey 1) C4216
ms.date: 11/04/2016
f1_keywords:
- C4216
helpviewer_keywords:
- C4216
ms.assetid: 211079dc-59d0-42a7-801c-2ddab21d7232
ms.openlocfilehash: b7fc44fd15f761c19ed28402a41b3bd3619b21a0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223271"
---
# <a name="compiler-warning-level-1-c4216"></a>Derleyici Uyarısı (düzey 1) C4216

Standart olmayan uzantı kullanıldı: float Long

Varsayılan Microsoft uzantıları (/Ze), **float süresini** olarak değerlendirir **`double`** . ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) değil. **`double`** Uyumluluğu korumak için kullanın. Aşağıdaki örnek C4216 oluşturur:

```cpp
// C4216.cpp
// compile with: /W1
float long a;   // C4216

// use the line below to resolve the warning
// double a;

int main() {
}
```
