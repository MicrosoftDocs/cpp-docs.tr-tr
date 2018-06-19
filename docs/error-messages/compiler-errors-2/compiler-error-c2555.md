---
title: Derleyici Hatası C2555 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2555
dev_langs:
- C++
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d2d1a710177e2c8c72b0afeff662dddf1c22ef5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230593"
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