---
title: "Derleyici Hatası C2233 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2233
dev_langs: C++
helpviewer_keywords: C2233
ms.assetid: 236bdf0b-9607-4f26-a249-d8def0b1333c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9b83a0036667ed0bb7e30cc140cb3d4c38c5712b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2233"></a>Derleyici Hatası C2233
'tanımlayıcısı': Geçersiz sıfır boyutlu diziler içeren nesne dizileri  
  
 Dizideki her nesnenin en az bir öğe içermesi gerekir.  
  
 Aşağıdaki örnek C2233 oluşturur:  
  
```  
// C2233.cpp  
// compile with: /c  
class A {  
   char somearray[1];  
};  
  
class B {  
   char zeroarray[];  
};  
  
A array[100];   // OK  
B array2[100];   // C2233  
```