---
title: Derleyici Hatası C2166 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2166
dev_langs:
- C++
helpviewer_keywords:
- C2166
ms.assetid: 12789c3a-cc76-48bb-ae2e-64283e0964ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9902110832c3c8c8126fcb45e21881449206941c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096866"
---
# <a name="compiler-error-c2166"></a>Derleyici Hatası C2166

lvalue, const nesnesi belirtiyor.

Kod öğesi bildirilmiş bir değiştirme girişiminde `const`.

Aşağıdaki örnek, C2166 oluşturur:

```
// C2166.cpp
int f();
int main() {
   ( (const int&) 1 ) = 5;   // C2166
}
```