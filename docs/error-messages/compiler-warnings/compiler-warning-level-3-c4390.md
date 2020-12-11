---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4390'
title: Derleyici Uyarısı (düzey 3) C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 8067d4beae44e098085122968a227f6ff8bc8b4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160447"
---
# <a name="compiler-warning-level-3-c4390"></a>Derleyici Uyarısı (düzey 3) C4390

'; ': boş denetimli ifade bulundu; Bu amaç mı?

Hiçbir yönerge içermeyen bir denetim ifadesinden sonra noktalı virgül bulundu.

Bir makro nedeniyle C4390 alırsanız, makroyu içeren modülde C4390 'yi devre dışı bırakmak için [Warning](../../preprocessor/warning.md) pragma öğesini kullanmanız gerekir.

Aşağıdaki örnek C4390 oluşturur:

```cpp
// C4390.cpp
// compile with: /W3
int main() {
   int i = 0;
   if (i);   // C4390
      i++;
}
```
