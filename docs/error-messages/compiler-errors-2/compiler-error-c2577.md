---
title: "Derleyici Hatası C2577 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2577
dev_langs: C++
helpviewer_keywords: C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: df2e681274c21b639c6b188346b355167de7ce03
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2577"></a>Derleyici Hatası C2577
'member': yıkıcı/sonlandırıcıyı bir dönüş türüne sahip olamaz  
  
 Yıkıcı veya sonlandırıcıyı değerini geri dönemezsiniz `void` veya başka bir türü. Kaldırma `return` yıkıcı tanımından deyimi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2577 oluşturur.  
  
```  
// C2577.cpp  
// compile with: /c  
class A {  
public:  
   A() {}  
   ~A(){  
      return 0;   // C2577  
   }  
};  
```