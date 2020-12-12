---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4558'
title: Derleyici Uyarısı (düzey 1) C4558
ms.date: 11/04/2016
f1_keywords:
- C4558
helpviewer_keywords:
- C4558
ms.assetid: 52bb0324-7bec-468c-b35b-13a08d38e578
ms.openlocfilehash: b35f127daad10d0346a8adc30e712d6de56d5805
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173681"
---
# <a name="compiler-warning-level-1-c4558"></a>Derleyici Uyarısı (düzey 1) C4558

' Value ' işleneni değeri, ' albağı-üst sınırı ' aralığının dışında

Bir derleme dili yönergesine geçirilen değer, parametre için belirtilen aralığın dışında. Değer kesilecek.

Aşağıdaki örnek C4558 oluşturur:

```cpp
// C4558.cpp
// compile with: /W1
// processor: x86
void asm_test() {
   __asm pinsrw   mm1, eax, 8;   // C4558
}

int main() {
}
```
