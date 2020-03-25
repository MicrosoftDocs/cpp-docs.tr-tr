---
title: Derleyici Uyarısı (düzey 3) C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 63150f4ca801d3c377c7bc09b58a778bebf02b46
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198685"
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
