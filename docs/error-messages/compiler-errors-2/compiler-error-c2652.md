---
title: "Derleyici Hatası C2652 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2652
dev_langs:
- C++
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b470511c6d9a654357d0c8007083a2d754e300ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2652"></a>Derleyici Hatası C2652
'tanımlayıcısı': Geçersiz kopya Oluşturucu: ilk parametre 'tanımlayıcı' olmamalıdır  
  
 Kopya Oluşturucu ilk parametreyi sınıf, yapı veya UNION, tanımlandığı aynı türe sahip. İlk parametre türü ancak türün kendisine bir başvuru olabilir.  
  
 Aşağıdaki örnek C2651 oluşturur:  
  
```  
// C2652.cpp  
// compile with: /c  
class A {  
   A( A );   // C2652 takes an A  
};  
class B {  
   B( B& );   // OK, reference to B  
};  
```