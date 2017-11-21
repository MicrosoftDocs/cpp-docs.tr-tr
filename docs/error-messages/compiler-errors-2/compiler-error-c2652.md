---
title: "Derleyici Hatası C2652 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2652
dev_langs: C++
helpviewer_keywords: C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 56cfdf52ec3a6947a6a82774f551fc1a6880c959
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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