---
title: Derleyici Uyarısı (Düzey 3) C4334 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4334
dev_langs:
- C++
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b7bb16ea38b2c2112c12c561398341a7d1adbfc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044021"
---
# <a name="compiler-warning-level-3-c4334"></a>Derleyici Uyarısı (Düzey 3) C4334

'operator': 32-bit kaydırmanın sonucu örtük olarak 64 bite dönüştürüldü (64-bit kaydırmanın hedeflenen oldu mu?)

32-bit kaydırmanın sonucu örtük olarak 64-bit ve 64-bit kaydırmanın tasarlanmıştı derleyici şüphelerini dönüştürüldü.  Bu uyarıyı çözmek için 64-bit kaydırmanın kullanabilir veya 64-bit kaydırma sonucu açıkça dönüştürün.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4334 oluşturur.

```
// C4334.cpp
// compile with: /W3 /c
void SetBit(unsigned __int64 *p, int i) {
   *p |= (1 << i);   // C4334
   *p |= (1i64 << i);   // OK
}
```