---
title: Derleyici Uyarısı (düzey 1) C4186 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4186
dev_langs:
- C++
helpviewer_keywords:
- C4186
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0bfc722a07d2ddb10e5be8c6d8fde60956b297c8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079784"
---
# <a name="compiler-warning-level-1-c4186"></a>Derleyici Uyarısı (düzey 1) C4186

\#içeri aktarma öznitelik 'özniteliği' sayısı bağımsız değişkenler gerektiriyor; yoksayıldı

A `#import` özniteliğinde yanlış sayıda bağımsız değişken.

## <a name="example"></a>Örnek

```
// C4186.cpp
// compile with: /W1 /c
#import "stdole2.tlb" no_namespace("abc") rename("a","b","c")  // C4186
```

`no_namespace` Özniteliği bağımsız değişken alır. **Yeniden Adlandır** özniteliği yalnızca iki bağımsız değişken alır.