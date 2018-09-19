---
title: Derleyici Uyarısı (düzey 1) C4312 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4312
dev_langs:
- C++
helpviewer_keywords:
- C4312
ms.assetid: 541906ed-4f62-4bcb-947f-cf9ae7411bcb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b6b6032ac22233c1662c6a7cc94d5ade7ae3a98
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095358"
---
# <a name="compiler-warning-level-1-c4312"></a>Derleyici Uyarısı (düzey 1) C4312

'operation' : 'type1' öğesinden daha büyük boyutlu 'type2' öğesine dönüştürme

Bu uyarı bir 32-bit atama 64-bit işaretçi türü için örneğin, 32-bit bir değer atamak için bir deneme algılar `int` veya `long` 64-bit işaretçi.

Bu, güvenli olmayan bir dönüştürme bile 32 bit imza uzantısı oluştuğunda uyan işaretçi değerleri olabilir. Negatif bir 32 bit tamsayı bir 64-bit işaretçi türüne atanan işaret uzantısı tamsayı değerinden farklı bir bellek adresi başvurusu işaretçi değeri neden olur.

Bu uyarı, yalnızca 64 bit derleme hedefleri için görüntülenir. Daha fazla bilgi için [kullanarak işaretçileri için kuralları](/windows/desktop/WinProg64/rules-for-using-pointers).

Aşağıdaki kod örneği, 64-bit hedefleri için derlendiğinde C4312 oluşturur:

```
// C4312.cpp
// compile by using: cl /W1 /LD C4312.cpp
void* f(int i) {
   return (void*)i;   // C4312 for 64-bit targets
}

void* f2(__int64 i) {
   return (void*)i;   // OK
}
```