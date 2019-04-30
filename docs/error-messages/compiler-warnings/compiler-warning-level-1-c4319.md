---
title: Derleyici Uyarısı (düzey 1) C4319
ms.date: 1/18/2018
f1_keywords:
- C4319
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
ms.openlocfilehash: 20b268bacd6e7e259e9b4fa1c9e98fa6fd353718
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385478"
---
# <a name="compiler-warning-level-1-c4319"></a>Derleyici Uyarısı (düzey 1) C4319

> ' ~': sıfır genişletme '*type1*'to'*type2*' daha büyük boyutlu

Sonucu **~** (bit düzeyinde tamamlayıcı) işleci, işaretsiz ve ardından sıfır genişletilmiş daha büyük bir türe dönüştürüldüğünde.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, `~(a - 1)` 32 bitlik bir işaretsiz uzun ifade olarak değerlendirilir ve sonra da sıfır uzantısı tarafından 64 bit dönüştürülür. Bu işlem beklenmeyen sonuçlara neden olabilir.

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
