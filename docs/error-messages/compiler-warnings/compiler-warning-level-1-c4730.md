---
title: "Derleyici Uyarısı (düzey 1) C4730 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4730
dev_langs:
- C++
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 334c53b030097dc822451b0e555a51c90e70d904
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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