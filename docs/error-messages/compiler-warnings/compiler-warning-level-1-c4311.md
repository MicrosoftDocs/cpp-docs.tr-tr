---
title: Derleyici Uyarısı (düzey 1) C4311
ms.date: 11/04/2016
f1_keywords:
- C4311
helpviewer_keywords:
- C4311
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
ms.openlocfilehash: f60daa66daa42687522400284a19ec87eb13f67c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513730"
---
# <a name="compiler-warning-level-1-c4311"></a>Derleyici Uyarısı (düzey 1) C4311

'variable' : 'type' öğesinden 'type' öğesine işaretçi kesilmesi

Bu uyarı, 64-bit işaretçi kesilmesi sorunları algılar. Bir 64 bit mimari için kod derlenir, atanan, örneğin, bir işaretçi (64 bit) değeri kesilecek bir `int` (32 bit). Daha fazla bilgi için [kullanarak işaretçileri için kuralları](/windows/desktop/WinProg64/rules-for-using-pointers).

Uyarı C4311 yaygın nedenleri hakkında ek bilgi için bkz: [Genel derleyici hataları](/windows/desktop/WinProg64/common-compiler-errors).

Aşağıdaki kod örneği için 64 bit hedef derlendiğinde C4311 oluşturur ve ardından sorunu gidermek nasıl gösterir:

```
// C4311.cpp
// compile by using: cl /W1 C4311.cpp
int main() {
   void* p = &p;
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets
   unsigned long long j = (unsigned long long) p;   // OK
}

```