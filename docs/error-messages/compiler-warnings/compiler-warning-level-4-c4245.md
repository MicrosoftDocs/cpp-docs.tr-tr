---
title: Derleyici Uyarısı (düzey 4) C4245 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4245
dev_langs:
- C++
helpviewer_keywords:
- C4245
ms.assetid: 85083d53-9cc2-4d12-b58c-6dad28f15cbe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b069e728a7bb70fb757d55b10ce3e9bdd189a8f9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055578"
---
# <a name="compiler-warning-level-4-c4245"></a>Derleyici Uyarısı (düzey 4) C4245

'conversion': 'type1' öğesinden 'type2', imzalı/imzasız uyuşmazlığı dönüştürme

İmzalı bir dönüştürmeyi denedi **const** negatif bir değere sahip bir `unsigned`.

Aşağıdaki örnek, C4245 oluşturur:

```
// C4245.cpp
// compile with: /W4 /c
const int i = -1;
unsigned int j = i; // C4245

const int k = 1;
unsigned int l = k; // okay

int m = -1;
unsigned int n = m; // okay

void Test(size_t i) {}

int main() {
   Test( -19 );   // C4245
}
```