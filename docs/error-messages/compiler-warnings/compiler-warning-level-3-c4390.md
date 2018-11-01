---
title: Derleyici Uyarısı (Düzey 3) C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 4ca00f892adc8fe3ac1bffb59a27ea1744249dea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479527"
---
# <a name="compiler-warning-level-3-c4390"></a>Derleyici Uyarısı (Düzey 3) C4390

';': boş denetlenen deyim bulundu; Bu amaç mi?

Noktalı virgül, hiçbir yönergeleri içeren bir denetim deyimidir sonra bulunamadı.

Makro nedeniyle C4390 alırsanız, kullanmanız gereken [uyarı](../../preprocessor/warning.md) pragma makro içeren modülünde C4390 devre dışı bırakmak için.

Aşağıdaki örnek, C4390 oluşturur:

```
// C4390.cpp
// compile with: /W3
int main() {
   int i = 0;
   if (i);   // C4390
      i++;
}
```