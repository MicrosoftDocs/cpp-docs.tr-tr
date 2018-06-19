---
title: Derleyici Uyarısı (düzey 1) C4319 | Microsoft Docs
ms.custom: ''
ms.date: 1/18/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4319
dev_langs:
- C++
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c1b5fe896ae7d8f43708b60ee4dda486ef08f428
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284751"
---
# <a name="compiler-warning-level-1-c4319"></a>Derleyici Uyarısı (düzey 1) C4319

> ' ~': sıfır genişletme '*type1*'to'*type2*' büyük boyutu

Sonucu **~** (bit düzeyinde tamamlama) işleci, imzasız ve ardından sıfır genişletilmiş daha büyük bir türe dönüştürüldüğünde.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, `~(a - 1)` 32-bit bir imzasız uzun ifade olarak değerlendirilir ve 64 bit sıfır uzantısı tarafından sonra dönüştürülür. Bu, beklenmeyen işlem sonuçlara neden.

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
