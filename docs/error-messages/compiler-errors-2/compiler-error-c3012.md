---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3012'
title: Derleyici hatası C3012
ms.date: 11/04/2016
f1_keywords:
- C3012
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
ms.openlocfilehash: fff986a984acb62f770d02ff2b7b08c40e8511e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286013"
---
# <a name="compiler-error-c3012"></a>Derleyici hatası C3012

> '*Intrinsic*': doğrudan bir paralel bölgenin içinde iç işleve izin verilmiyor

Bir bölgede [derleyici iç](../../intrinsics/compiler-intrinsics.md) işlevine izin verilmez `omp parallel` . Bu sorunu onarmak için, iç öğeleri bölgenin dışına taşıyın veya gerçek olmayan eşdeğerleriyle değiştirin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3012 oluşturur ve bunu çözmek için bir yol gösterir:

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
