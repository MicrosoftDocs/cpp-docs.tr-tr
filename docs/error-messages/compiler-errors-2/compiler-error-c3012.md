---
title: Derleyici Hatası C3012
ms.date: 11/04/2016
f1_keywords:
- C3012
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
ms.openlocfilehash: 9fe0ac7d3637cad3a5571c4631345dac1a0021bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386739"
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