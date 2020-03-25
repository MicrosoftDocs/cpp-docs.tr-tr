---
title: Derleyici hatası C3012
ms.date: 11/04/2016
f1_keywords:
- C3012
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
ms.openlocfilehash: 69f0544815804e9827631be81bf9735a95bd1a22
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176708"
---
# <a name="compiler-error-c3012"></a>Derleyici hatası C3012

> '*Intrinsic*': doğrudan bir paralel bölgenin içinde iç işleve izin verilmiyor

Bir `omp parallel` bölgesinde [derleyici iç](../../intrinsics/compiler-intrinsics.md) işlevine izin verilmez. Bu sorunu onarmak için, iç öğeleri bölgenin dışına taşıyın veya gerçek olmayan eşdeğerleriyle değiştirin.

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
