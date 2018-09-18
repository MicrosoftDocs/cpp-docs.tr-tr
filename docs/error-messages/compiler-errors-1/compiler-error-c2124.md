---
title: Derleyici Hatası C2124 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2124
dev_langs:
- C++
helpviewer_keywords:
- C2124
ms.assetid: 93392aaa-5582-4d68-8cc5-bd9c62a0ae7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7810565a8f7bfdac49f2c53815b9063e2e034df7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062330"
---
# <a name="compiler-error-c2124"></a>Derleyici Hatası C2124

bölme veya mod alma sıfıra

Bir sabit ifade bir sıfır paydası sahiptir. Hatayı gidermek için sıfır bölmeyin.

Aşağıdaki örnek, C2124 oluşturur:

```
// C2124.cpp
int main() {
  int i = 1 / 0;   // C2124  do not divide by zero
  int i2 = 12 / 2;   // OK
}
```