---
title: Derleyici Hatası C2267 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2267
dev_langs:
- C++
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 080f6ebfda8dbdaa1f0bf70faa3b6d5c7545d66e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035272"
---
# <a name="compiler-error-c2267"></a>Derleyici Hatası C2267

'function': blok kapsamı olan statik işlevler geçersizdir

Yerel bir işlev bildirildiği `static`. Statik işlevler genel kapsamda olması gerekir.

Aşağıdaki örnek, C2267 oluşturur:

```
// C2267.cpp
static int func2();   // OK
int main() {
    static int func1();   // C2267
}
```