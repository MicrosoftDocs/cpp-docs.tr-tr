---
title: Derleyici Uyarısı (düzey 1 ve düzey 4) C4949
ms.date: 11/04/2016
f1_keywords:
- C4949
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
ms.openlocfilehash: 8050edbd7a653776d046bc7b4155fd43094d9a5d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187528"
---
# <a name="compiler-warning-level-1-and-level-4-c4949"></a>Derleyici Uyarısı (düzey 1 ve düzey 4) C4949

'managed' ve 'unmanaged' pragmaları yalnızca ile derlendikleri zaman anlamlıdır ' / clr [: option]'

Derleyicinin yoksaydığı [yönetilen](../../preprocessor/managed-unmanaged.md) ve ile kaynak kodu derlenmemişse pragmaları yönetilmeyen [/CLR](../../build/reference/clr-common-language-runtime-compilation.md). Bu uyarı, bilgi amaçlıdır.

Aşağıdaki örnek, C4949 oluşturur:

```
// C4949.cpp
// compile with: /LD /W1
#pragma managed   // C4949
```

Zaman **yönetilmeyen #pragma** olmadan kullanılan **/CLR**, C4949 olan düzey 4 uyarısı.

Aşağıdaki örnek, C4949 oluşturur:

```
// C4949b.cpp
// compile with: /LD /W4
#pragma unmanaged   // C4949
```