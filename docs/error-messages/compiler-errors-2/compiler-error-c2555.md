---
title: "Derleyici Hatası C2555 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2555
dev_langs: C++
helpviewer_keywords: C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 64f66bf80e8e4b6ba7477691cb9675cec347807d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2555"></a>Derleyici Hatası C2555
'class1::function1': sanal işlevi geçersiz kılma dönüş türü farklıdır ve 'class2::function2' eşdeğişken değil  
  
 Bir sanal işleve ve türetilmiş bir geçersiz kılma işlevi farklı dönüş türleri ancak aynı parametre listeleri vardır. Bir geçersiz kılma işlevi türetilmiş bir sınıf içinde bir sanal işlev dönüş türü tarafından yalnızca bir taban sınıf içinde farklı olamaz.  
  
 Bu hatayı gidermek için sanal işlev çağrıldıktan sonra dönüş değerini atayın.  
  
 / CLR ile derleme yaparsanız, bu hatayı da görebilirsiniz.   Örneğin, Visual C++ aşağıdaki C# bildirimine eşdeğer:  
  
```  
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);  
```  
  
 is  
  
```  
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];  
```  
  
 Bilgi Bankası makalesi Q240862 C2555 hakkında daha fazla bilgi için bkz.  
  
 Aşağıdaki örnek C2555 oluşturur:  
  
```  
// C2555.cpp  
// compile with: /c  
struct X {  
   virtual void func();  
};  
struct Y : X {  
   char func();  // C2555  
   void func2();   // OK  
};  
```