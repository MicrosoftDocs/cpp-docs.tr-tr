---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4312'
title: Derleyici Uyarısı (düzey 1) C4312
ms.date: 11/04/2016
f1_keywords:
- C4312
helpviewer_keywords:
- C4312
ms.assetid: 541906ed-4f62-4bcb-947f-cf9ae7411bcb
ms.openlocfilehash: 52e165fd30a9171c1a08aa16f78cc1f298271b17
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340079"
---
# <a name="compiler-warning-level-1-c4312"></a>Derleyici Uyarısı (düzey 1) C4312

'operation' : 'type1' öğesinden daha büyük boyutlu 'type2' öğesine dönüştürme

Bu uyarı, 32 bitlik bir değeri 64 bit işaretçi türüne atama girişimini algılar, örneğin, 32-bit **`int`** veya **`long`** 64-bit işaretçisi atama.

Bu, oturum açma uzantısı gerçekleştiğinde 32 bite sığan işaretçi değerleri bile güvenli olmayan bir dönüştürme olabilir. Bir 64 bit işaretçi türüne negatif 32 bitlik bir tamsayı atanırsa, imza uzantısı, işaretçi değerinin tamsayının değerinden farklı bir bellek adresine başvurmasına neden olur.

Bu uyarı yalnızca 64 bitlik derleme hedefleri için verilir. Daha fazla bilgi için bkz. [Işaretçiler kullanma kuralları](/windows/win32/WinProg64/rules-for-using-pointers).

Aşağıdaki kod örneği 64-bit hedefler için derlendiğinde C4312 oluşturur:

```cpp
// C4312.cpp
// compile by using: cl /W1 /LD C4312.cpp
void* f(int i) {
   return (void*)i;   // C4312 for 64-bit targets
}

void* f2(__int64 i) {
   return (void*)i;   // OK
}
```
