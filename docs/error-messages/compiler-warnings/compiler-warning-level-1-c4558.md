---
title: Derleyici Uyarısı (düzey 1) C4558
ms.date: 11/04/2016
f1_keywords:
- C4558
helpviewer_keywords:
- C4558
ms.assetid: 52bb0324-7bec-468c-b35b-13a08d38e578
ms.openlocfilehash: 26bf1603588f522e2bec366586984896190f2d65
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162302"
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
