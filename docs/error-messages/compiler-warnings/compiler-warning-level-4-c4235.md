---
title: Derleyici Uyarısı (düzey 4) C4235
ms.date: 11/04/2016
f1_keywords:
- C4235
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
ms.openlocfilehash: df80bec2294929be463425d74d4bf00421b368e6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198438"
---
# <a name="compiler-warning-level-4-c4235"></a>Derleyici Uyarısı (düzey 4) C4235

Standart olmayan uzantı kullanıldı: ' anahtar sözcük ' anahtar sözcüğü Bu mimaride desteklenmiyor

Derleyici, kullandığınız anahtar sözcüğü desteklemez.

Bu uyarı otomatik olarak bir hataya yükseltilir. Bu davranışı değiştirmek isterseniz [#pragma uyarı](../../preprocessor/warning.md)kullanın. Örneğin, C4235 düzey 2 uyarısı oluşturmak için aşağıdaki kod satırını kullanın

```cpp
#pragma warning(2:4235)
```

kaynak kodu dosyanızda.
