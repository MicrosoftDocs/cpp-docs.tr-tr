---
title: Derleyici Hatası C3455
ms.date: 11/04/2016
f1_keywords:
- C3455
helpviewer_keywords:
- C3455
ms.assetid: 218e5cfe-5391-4eeb-81c2-85c47e3a6cd2
ms.openlocfilehash: 4451ddbd8d5a7125112ef8e1c58e8843095bffd4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614402"
---
# <a name="compiler-error-c3455"></a>Derleyici Hatası C3455

'attribute': öznitelik oluşturucularının hiçbiri bağımsız değişkenlerle eşleşmedi

Bir öznitelik bildirmek için geçersiz değer kullanıldı.  Bkz: [özniteliği](../../windows/attributes/attribute.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3455 oluşturur.

```
// C3455.cpp
// compile with: /clr /c
using namespace System;

[attribute("MyAt")]   // C3455
// try the following line instead
// [attribute(All)]
ref struct MyAttr {
   MyAttr() {}
};
```