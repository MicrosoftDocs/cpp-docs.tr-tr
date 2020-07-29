---
title: Derleyici Uyarısı (düzey 1) C4311
ms.date: 11/04/2016
f1_keywords:
- C4311
helpviewer_keywords:
- C4311
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
ms.openlocfilehash: bcb3650ca98922559f23c6c2536c3076cc522ad0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233281"
---
# <a name="compiler-warning-level-1-c4311"></a>Derleyici Uyarısı (düzey 1) C4311

'variable' : 'type' öğesinden 'type' öğesine işaretçi kesilmesi

Bu uyarı 64 bit işaretçi kesme sorunlarını algılar. Örneğin, kod 64 bitlik bir mimari için derlenmişse, bir işaretçiye (64 bit) atandığında, bir **`int`** (32 bit) değeri kesilir. Daha fazla bilgi için bkz. [Işaretçiler kullanma kuralları](/windows/win32/WinProg64/rules-for-using-pointers).

Uyarı C4311 genel nedenleri hakkında daha fazla bilgi için bkz. [yaygın derleyici hataları](/windows/win32/WinProg64/common-compiler-errors).

Aşağıdaki kod örneği, 64 bitlik bir hedef için derlendikten sonra C4311 oluşturur ve sonra bunu nasıl düzelteceğinizi gösterir:

```cpp
// C4311.cpp
// compile by using: cl /W1 C4311.cpp
int main() {
   void* p = &p;
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets
   unsigned long long j = (unsigned long long) p;   // OK
}
```
