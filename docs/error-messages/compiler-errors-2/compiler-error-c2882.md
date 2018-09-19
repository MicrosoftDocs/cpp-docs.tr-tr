---
title: Derleyici Hatası C2882 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2882
dev_langs:
- C++
helpviewer_keywords:
- C2882
ms.assetid: 617018ee-5a0d-4b8d-9612-77e8ae52679b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59110c6c196bfed2a268484af8a2de1e15552041
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025795"
---
# <a name="compiler-error-c2882"></a>Derleyici Hatası C2882

'name': ad alanı tanımlayıcısının ifade içinde geçersiz kullanımı

Bir ifadede bir ad alanı adını kullanmak denedi.

Aşağıdaki örnek, C2882 oluşturur:

```
// C2882.cpp
// compile with: /c
namespace A {
   int k;
}

int i = A;   // C2882, can't assign A to i
```