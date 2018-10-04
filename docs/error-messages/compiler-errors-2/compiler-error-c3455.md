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
ms.openlocfilehash: a10c91f34cd00b8524a047131e9a39b901c83fce
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788597"
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