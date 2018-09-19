---
title: Derleyici Hatası C2341 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2341
dev_langs:
- C++
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adac1e6f6e5f5d58b6091a389537a42f0e496b31
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020205"
---
# <a name="compiler-error-c2341"></a>Derleyici Hatası C2341

'bölüm adı': kesim kullanmak için kullanılmadan önce #pragma data_seg, code_seg veya section kullanılarak tanımlanmalıdır

Bir [tahsis](../../cpp/allocate.md) deyimi tarafından henüz tanımlanmamış bir segment başvurduğu [code_seg](../../preprocessor/code-seg.md), [data_seg](../../preprocessor/data-seg.md), veya [bölümü](../../preprocessor/section.md) pragmaları.

Aşağıdaki örnek, C2341 oluşturur:

```
// C2341.cpp
// compile with: /c
__declspec(allocate(".test"))   // C2341
int j = 1;
```

Olası çözüm:

```
// C2341b.cpp
// compile with: /c
#pragma data_seg(".test")
__declspec(allocate(".test"))
int j = 1;
```