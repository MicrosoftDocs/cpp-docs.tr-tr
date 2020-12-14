---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4405'
title: Derleyici Uyarısı (düzey 1) C4405
ms.date: 11/04/2016
f1_keywords:
- C4405
helpviewer_keywords:
- C4405
ms.assetid: 155c64d6-58ae-4455-b61f-ccd711c5da96
ms.openlocfilehash: 53b70ea7d3e55ed23f398c912daeb69827715a58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311090"
---
# <a name="compiler-warning-level-1-c4405"></a>Derleyici Uyarısı (düzey 1) C4405

' tanımlayıcı ': tanımlayıcı ayrılmış bir sözcük

Satır içi derleme için ayrılmış bir sözcük, değişken adı olarak kullanılır. Bu durum öngörülemeyen sonuçlara neden olabilir. Bu uyarıyı onarmak için, satır içi derleme için ayrılmış sözcüklerin bulunduğu adlandırma değişkenleri kullanmaktan kaçının. Aşağıdaki örnek C4405 oluşturur:

```cpp
// C4405.cpp
// compile with: /W1
// processor: x86
void func1() {
   int mov = 0, i = 0;
   _asm {
      mov mov, 0;   // C4405
      // instead, try ..
      // mov i, 0;
   }
}

int main() {
}
```
