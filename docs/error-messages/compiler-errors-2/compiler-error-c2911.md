---
title: "Derleyici Hatası C2911 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2911
dev_langs: C++
helpviewer_keywords: C2911
ms.assetid: 83c7c01a-ab6a-4179-9fb0-289a9ec8d44e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4b4cb6026584424391ba9c68b24d25f130380eb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2911"></a>Derleyici Hatası C2911
'member': bildirilen veya geçerli kapsamda tanımlı  
  
 Bir ad alanı, sınıf veya işlev içinde yalnızca aynı ad alanı, sınıf veya işlevi bir üyesi ya da aynı ad alanı, sınıf veya işlevi tarafından içine üyesi tanımlayabilirsiniz.  
  
 Aşağıdaki örnek C2911 oluşturur:  
  
```  
// C2911.cpp  
struct A;  
  
namespace M {  
   struct D;  
}  
  
namespace N {  
   struct C;  
  
   namespace O {  
      struct B;  
   }  
  
   // in N  
   struct ::A {};   // C2911  A is member of global NS  
   struct O::B{};   // OK B is in O, O is inside of N  
   struct C {};     // OK C is member of N  
   struct M::D {};  // C2911 D is member of M, M not enclosed by N  
}  
```