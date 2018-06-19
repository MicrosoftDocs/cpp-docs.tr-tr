---
title: Derleyici Uyarısı (düzey 1) C4964 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4964
dev_langs:
- C++
helpviewer_keywords:
- C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98226b2da465d2301356939273d370d76edcb64e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290322"
---
# <a name="compiler-warning-level-1-c4964"></a>Derleyici Uyarısı (düzey 1) C4964
En iyi duruma getirme seçenekleri belirtildi; profil bilgileri toplanmaz  
  
 [/GL](../../build/reference/gl-whole-program-optimization.md) ve [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) herhangi bir iyileştirme belirtilmiş hiçbir .pgc dosya oluşturulur ve bu nedenle, hiçbir profil temelli iyileştirmeler kullanılabilecektir şekilde istendi.  
  
 Uygulamanızı çalıştırdığınızda oluşturulacak .pgc dosyaları istiyorsanız, aşağıdakilerden birini belirtin [/O](../../build/reference/o-options-optimize-code.md) derleyici seçenekleri.  
  
 Aşağıdaki örnek C4964 oluşturur:  
  
```  
// C4964.cpp  
// compile with: /W1 /GL /link /ltcg:pgi  
// C4964 expected  
// Add /O2, for example, to the command line to resolve this warning.  
int main() {  
   int i;  
}  
```