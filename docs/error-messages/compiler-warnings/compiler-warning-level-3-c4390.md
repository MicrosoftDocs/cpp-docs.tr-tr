---
title: Derleyici Uyarısı (düzey 3) C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 8402c6a2d0fcbb4704b833ac7ae2b070c7af3a48
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051599"
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