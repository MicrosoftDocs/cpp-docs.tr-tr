---
title: "Derleyici Hatası C2587 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2587
dev_langs: C++
helpviewer_keywords: C2587
ms.assetid: 7637a2c7-35d4-4b5a-a8f2-515a7bda98fd
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 127c66017fdc961c63051e67ee6a4f62b0b3e789
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2587"></a>Derleyici Hatası C2587
'tanımlayıcısı': geçersiz kullanımı yerel değişkene varsayılan parametre olarak  
  
 Yerel değişkenler varsayılan parametreler olarak izin verilmez.  
  
 Aşağıdaki örnek C2587 oluşturur:  
  
```  
// C2587.cpp  
// compile with: /c  
int i;  
void func() {  
   int j;  
   extern void func2( int k = j );  // C2587 -- local variable  
   extern void func3( int k = i );   // OK  
}  
```