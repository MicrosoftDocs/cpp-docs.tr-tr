---
title: Derleyici Hatası C3012 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3012
dev_langs:
- C++
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99bdac5ffb75978479ae7ef420a48b3d1b2f8e64
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063677"
---
# <a name="compiler-error-c3012"></a>Derleyici Hatası C3012

> '*iç*': iç işlev doğrudan bir paralel bölgenin içinde izin verilmiyor

A [iç derleyici](../../intrinsics/compiler-intrinsics.md) işlevine izin verilmiyor bir `omp parallel` bölge. Bu sorunu gidermek için yapı içleri bölgesinin dışına taşıyın veya bunları iç olmayan eşdeğerleriyle değiştirin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3012 oluşturur ve bunu çözmenin yollarından biri gösterilmektedir:

```cpp
// C3012.cpp
// compile with: /openmp
#ifdef __cplusplus
extern "C" {
#endif
void* _ReturnAddress();
#ifdef __cplusplus
}
#endif

int main()
{
   #pragma omp parallel
   {
      _ReturnAddress();   // C3012
   }
   _ReturnAddress();      // OK
}
```