---
title: Derleyici Uyarısı (düzey 1 ve düzey 4) C4949 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4949
dev_langs:
- C++
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f806912188ada3a4f97f0b1500e811d1271f40fe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077314"
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