---
title: "Derleyici Hatası C2318 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2318
dev_langs: C++
helpviewer_keywords: C2318
ms.assetid: 169e30b9-df78-46cb-90bf-576ad3c32fd4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d6fdb2888250b8833f1c5825fa6570d30d681c1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2318"></a>Derleyici Hatası C2318
Bu yakalama işleyici ile ilişkili herhangi bir try engelleme  
  
 A `catch` işleyici tanımlı ancak öncesinde olmayan bir `try` bloğu.  
  
 Aşağıdaki örnek C2318 oluşturur:  
  
```  
// C2318.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   // no try block  
   catch( int ) {}   // C2318  
}  
```  
  
 Olası çözüm:  
  
```  
// C2318b.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   try{}  
   catch( int ) {}  
}  
```