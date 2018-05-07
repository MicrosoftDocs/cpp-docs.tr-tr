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
ms.openlocfilehash: 4d30a7fbb50a984c8cec6b45a0ab4759a0578de7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3012"></a>Derleyici Hatası C3012
  
> '*iç*': doğrudan paralel bir bölge içinde izin verilmiyor iç işlevi  
  
 A [iç derleyici](../../intrinsics/compiler-intrinsics.md) işlevi izin verilmeyen bir `omp parallel` bölge. Bu sorunu gidermek için yapı bölgesinin dışına taşıyın veya iç olmayan eşdeğerleriyle değiştirin.   
  
## <a name="example"></a>Örnek  
  
 Aşağıdaki örnek C3012 oluşturur ve bu düzeltmenin bir yolu gösterir:  
  
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