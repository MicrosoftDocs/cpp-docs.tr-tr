---
title: Derleyici Uyarısı (düzey 1) C4311
ms.date: 11/04/2016
f1_keywords:
- C4311
helpviewer_keywords:
- C4311
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
ms.openlocfilehash: 5f9b8ce710879913fdad1be5c0f22f8e3f4ed9d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408335"
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