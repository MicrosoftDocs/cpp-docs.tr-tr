---
title: Derleyici Uyarısı (düzey 4) C4937 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4937
dev_langs:
- C++
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ed7b33889677a304d303873799f36430c38129a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33294937"
---
# <a name="compiler-warning-level-4-c4937"></a>Derleyici Uyarısı (düzey 4) C4937
'Metin1' ve 'Metin2' 'yönergesi' bağımsız değişken olarak ayırt  
  
 Yol nedeniyle derleyici yönergeleri, birden çok metin şekillerini (tek ve çift alt çizgi formlar) ile anahtar sözcükler gibi derleyici anlamı, ayırt edici olamaz adları bağımsız değişkenleri işler.  
  
 Bu tür dizeleri örnekler __cdecl ve \__forceinline.  , Yalnızca çift alt çizgi formları etkin /Za altında unutmayın.  
  
 Aşağıdaki örnek C4937 oluşturur:  
  
```  
// C4937.cpp  
// compile with: /openmp /W4  
#include "omp.h"  
int main() {  
   #pragma omp critical ( __leave )   // C4937  
   ;  
  
   // OK  
   #pragma omp critical ( leave )  
   ;  
}  
```