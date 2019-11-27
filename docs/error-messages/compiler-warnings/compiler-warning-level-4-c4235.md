---
title: Derleyici Uyarısı (düzey 4) C4235
ms.date: 11/04/2016
f1_keywords:
- C4235
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
ms.openlocfilehash: 3e3cb2e40ed42b24ee52252003b26ec09cd86710
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541755"
---
# <a name="compiler-warning-level-4-c4235"></a>Derleyici Uyarısı (düzey 4) C4235

Standart olmayan uzantı kullanıldı: ' anahtar sözcük ' anahtar sözcüğü Bu mimaride desteklenmiyor

Derleyici, kullandığınız anahtar sözcüğü desteklemez.

Bu uyarı otomatik olarak bir hataya yükseltilir. Bu davranışı değiştirmek isterseniz [#pragma uyarı](../../preprocessor/warning.md)kullanın. Örneğin, C4235 düzey 2 uyarısı oluşturmak için aşağıdaki kod satırını kullanın

```cpp
#pragma warning(2:4235)
```

kaynak kodu dosyanızda.