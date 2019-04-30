---
title: Derleyici Uyarısı (düzey 4) C4234
ms.date: 11/04/2016
f1_keywords:
- C4234
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
ms.openlocfilehash: 314ee068fb2be6148304360b0aaa3bd8029c283b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401078"
---
# <a name="compiler-warning-level-4-c4234"></a>Derleyici Uyarısı (düzey 4) C4234

Standart olmayan uzantı kullanıldı: 'anahtar sözcüğü' anahtar sözcüğü gelecekte kullanılmak üzere ayrılmış

Derleyici, kullanılan anahtar sözcüğü henüz uygulamıyor.

Bu uyarı, bir hata için otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, [#pragma Uyarısı](../../preprocessor/warning.md). Örneğin, bir düzey 4 uyarısı sorunu C4234 yapmak için

```
#pragma warning(2:4234)
```

Kaynak kodu dosyanızda.