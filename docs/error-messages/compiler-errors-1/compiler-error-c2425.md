---
title: Derleyici Hatası C2425
ms.date: 11/04/2016
f1_keywords:
- C2425
helpviewer_keywords:
- C2425
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
ms.openlocfilehash: fcbcf06df3330320bf014c132abc543e2e2e8087
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479033"
---
# <a name="compiler-error-c2425"></a>Derleyici Hatası C2425

'token': 'bağlamında' sabit olmayan ifade

Belirteç, bu bağlamda bir sabit olmayan ifade parçası oluşturur.

Bu sorunu gidermek için belirteci bir hesaplama veya bir sabit hazır değeri ile değiştirin.

Aşağıdaki örnek, C2425 oluşturur:

```
// C2425.cpp
// processor: x86
int main() {
   int i = 3;
   __asm {
      mov eax, [ebp - i]   // C2425
      mov eax, [ebp - 3]   // OK
   }
}
```