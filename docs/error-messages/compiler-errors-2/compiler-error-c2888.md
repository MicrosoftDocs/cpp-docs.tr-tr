---
title: Derleyici Hatası C2888 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2888
dev_langs:
- C++
helpviewer_keywords:
- C2888
ms.assetid: 244f593e-ff25-4dad-b31f-84dafa3bc84a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1d083ba049558c08c6070d13d0d7a61ad319add0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33242176"
---
# <a name="compiler-error-c2888"></a>Derleyici Hatası C2888
'tanımlayıcısı': 'namespace' ad alanı içinde Sembol tanımlanamıyor  
  
 A. kapsayan bir ad alanında bir ad alanına ait bir simge tanımlanmalıdır  
  
 Aşağıdaki örnek C2888 oluşturur:  
  
```  
// C2888.cpp  
// compile with: /c  
namespace M {  
   namespace N {  
      void f1();  
      void f2();  
   }  
  
   void N::f1() {}   // OK: namspace M encloses N  
}  
  
namespace O {  
   void M::N::f2() {}   // C2888 namespace O does not enclose M  
}  
```