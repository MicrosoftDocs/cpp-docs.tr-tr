---
title: Derleyici Uyarısı (düzey 1) C4730 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4730
dev_langs:
- C++
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 467d9fd04e2fef78d480fc4db1417b6e4c8d5641
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4730"></a>Derleyici Uyarısı (Düzey 1) C4730
'ana': _m64 karıştırma ve kayan nokta ifadeleri yanlış kodda neden olabilir  
  
 Bir işlev kullanan [__m64](../../cpp/m64.md) ve **float**/**çift** türleri. Kayan nokta kaydeder ve MMX aynı fiziksel paylaştığından alanı kaydetmek (aynı anda, kullanarak kullanılamaz) `__m64` ve **float**/**çift** aynı türleri işlevi, büyük olasılıkla bir özel duruma neden verilerin bozulmasına yol açabilir.  
  
 Güvenli bir şekilde kullanmak için `__m64` türleri ve aynı işlevde kayan nokta türleri, türlerinden birini kullanan her yönerge ayırarak **_m_empty()** (için MMX) veya **_m_femms()** (için 3DNow!) İç.  
  
 Aşağıdaki örnek C4730 oluşturur:  
  
```  
// C4730.cpp  
// compile with: /W1  
// processor: x86  
#include "mmintrin.h"  
  
void func(double)  
{  
}  
  
int main(__m64 a, __m64 b)  
{  
   __m64 m;  
   double f;  
   f = 1.0;  
   m = _m_paddb(a, b);  
   // uncomment the next line to resolve C4730  
   // _m_empty();  
   func(f * 3.0);   // C4730  
}  
```