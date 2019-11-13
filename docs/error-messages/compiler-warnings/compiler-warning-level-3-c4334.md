---
title: Derleyici Uyarısı (düzey 3) C4334
ms.date: 11/04/2016
f1_keywords:
- C4334
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
ms.openlocfilehash: ebebfe9994be3dd136e3924cb2aea60c0c901926
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051630"
---
# <a name="compiler-warning-level-3-c4334"></a>Derleyici Uyarısı (düzey 3) C4334

' operator ': 32 bitlik vardiyanın sonucu, örtülü olarak 64 bite dönüştürüldü (64-bit kaydırma amaçlıdır mi?)

32 bitlik vardiyanın sonucu, örtük olarak 64 bit 'e dönüştürüldü ve derleyici, bir 64-bit vardiyanın tasarlandığını şüphelendi.  Bu uyarıyı çözmek için 64 bitlik SHIFT kullanın veya SHIFT sonucunu açıkça 64 bit olarak atayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4334 oluşturur.

```cpp
// C4334.cpp
// compile with: /W3 /c
void SetBit(unsigned __int64 *p, int i) {
   *p |= (1 << i);   // C4334
   *p |= (1i64 << i);   // OK
}
```