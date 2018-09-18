---
title: Derleyici Hatası C3455 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3455
dev_langs:
- C++
helpviewer_keywords:
- C3455
ms.assetid: 218e5cfe-5391-4eeb-81c2-85c47e3a6cd2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d26a8f3e404eaa19a102be4cb3f11350c4fe674
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089365"
---
# <a name="compiler-error-c3455"></a>Derleyici Hatası C3455

'attribute': öznitelik oluşturucularının hiçbiri bağımsız değişkenlerle eşleşmedi

Bir öznitelik bildirmek için geçersiz değer kullanıldı.  Bkz: [özniteliği](../../windows/attribute.md) daha fazla bilgi için.

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