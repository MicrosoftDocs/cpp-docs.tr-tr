---
title: "Derleyici Uyarısı (düzey 1) C4624 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4624
dev_langs: C++
helpviewer_keywords: C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 643af7f0d95d86a073249529d73f62c6b07b04b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4624"></a>Derleyici Uyarısı (düzey 1) C4624
'türetilmiş bir sınıf': yıkıcı bir temel sınıf yıkıcı erişilemez veya silinmiş olduğundan silindi olarak örtük olarak tanımlanmıştı  
  
 Bir yıkıcı erişilebilir ya da bir taban sınıf içinde silinen değildi ve türetilmiş bir sınıf için oluşturulmamış. Yığında bu türde bir nesne oluşturma girişimi herhangi bir derleyici hatasına neden olur.  
  
 Aşağıdaki örnek C4624 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C4624.cpp  
// compile with: /W1 /c  
class B {  
// Uncomment the following line to fix.  
// public:  
   ~B();  
};  
  
class D : public B {};   // C4624 B's destructor not public  
```