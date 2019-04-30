---
title: Derleyici Uyarısı (düzey 4) C4235
ms.date: 11/04/2016
f1_keywords:
- C4235
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
ms.openlocfilehash: 80ad388b26b2b972aa1301c1f335d0361a75f15f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401052"
---
# <a name="compiler-warning-level-4-c4235"></a>Derleyici Uyarısı (düzey 4) C4235

Standart olmayan uzantı kullanıldı: 'anahtar sözcüğü' anahtar sözcüğü bu mimaride desteklenmiyor

Derleyici, kullanılan anahtar sözcüğü desteklemez.

Bu uyarı, bir hata için otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, [#pragma Uyarısı](../../preprocessor/warning.md). Örneğin, bir düzey 2 uyarı C4235 yapmak için aşağıdaki kod satırını kullanın.

```
#pragma warning(2:4235)
```

Kaynak kodu dosyanızda.