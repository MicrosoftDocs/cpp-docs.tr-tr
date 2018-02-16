---
title: "Derleyici Uyarısı (düzey 1) C4319 | Microsoft Docs"
ms.custom: 
ms.date: 1/18/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4319
dev_langs:
- C++
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a492194003a639f684e84d125450067cd425276
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="compiler-warning-level-1-c4319"></a>Derleyici Uyarısı (düzey 1) C4319

> ' ~': sıfır genişletme '*type1*'to'*type2*' büyük boyutu

Sonucu  **~**  (bit düzeyinde tamamlama) işleci, imzasız ve ardından sıfır genişletilmiş daha büyük bir türe dönüştürüldüğünde.

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
