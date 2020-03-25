---
title: Derleyici Uyarısı (düzey 1) C4186
ms.date: 11/04/2016
f1_keywords:
- C4186
helpviewer_keywords:
- C4186
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
ms.openlocfilehash: 6772e384b5908cbe81f85758f86eabe4c8240e6a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163329"
---
# <a name="compiler-warning-level-1-c4186"></a>Derleyici Uyarısı (düzey 1) C4186

' Attribute ' \#Import özniteliği Count bağımsız değişken gerektirir; LIP

`#import` özniteliğinde yanlış sayıda bağımsız değişken var.

## <a name="example"></a>Örnek

```cpp
// C4186.cpp
// compile with: /W1 /c
#import "stdole2.tlb" no_namespace("abc") rename("a","b","c")  // C4186
```

`no_namespace` öznitelik bağımsız değişken almaz. **Rename** özniteliği yalnızca iki bağımsız değişken alır.
