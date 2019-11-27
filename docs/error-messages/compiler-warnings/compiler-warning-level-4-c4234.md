---
title: Derleyici Uyarısı (düzey 4) C4234
ms.date: 11/04/2016
f1_keywords:
- C4234
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
ms.openlocfilehash: 63a22fed0832677837eb786268fc92946d295b79
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541771"
---
# <a name="compiler-warning-level-4-c4234"></a>Derleyici Uyarısı (düzey 4) C4234

Standart olmayan uzantı kullanıldı: daha sonra kullanılmak üzere ayrılmış ' anahtar sözcük ' anahtar sözcüğü

Derleyici henüz kullandığınız anahtar sözcüğü uygulamıyor.

Bu uyarı otomatik olarak bir hataya yükseltilir. Bu davranışı değiştirmek isterseniz [#pragma uyarı](../../preprocessor/warning.md)kullanın. Örneğin, C4234 4. düzey bir uyarı sorununa dönüştürmek için

```cpp
#pragma warning(2:4234)
```

kaynak kodu dosyanızda.