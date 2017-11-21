---
title: "Derleyici Hatası C2648 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2648
dev_langs: C++
helpviewer_keywords: C2648
ms.assetid: ce338337-9154-4f85-bb61-b05fdbfad75d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 99d52f3c07c0c20e49fa46baeba4cde618e286c7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2648"></a>Derleyici Hatası C2648
'tanımlayıcısı': statik üye varsayılan parametre gerektirdiği şekilde üyesi kullanın  
  
 Statik olmayan üye varsayılan parametre olarak kullanılır.  
  
 Aşağıdaki örnek C2648 oluşturur:  
  
```  
// C2648.cpp  
// compile with: /c  
class C {  
public:  
   int i;  
   static int j;  
   void func1( int i = i );  // C2648  i is not static  
   void func2( int i = j );  // OK  
};  
```