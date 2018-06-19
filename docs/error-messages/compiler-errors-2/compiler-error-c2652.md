---
title: Derleyici Hatası C2652 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2652
dev_langs:
- C++
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 576aef31268c0cdce09162fc367358e0ed044429
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232205"
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