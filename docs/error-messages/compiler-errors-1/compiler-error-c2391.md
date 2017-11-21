---
title: "Derleyici Hatası C2391 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2391
dev_langs: C++
helpviewer_keywords: C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 573cea44b0a39ff3cc0dff4469aa8c5f5a2459e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2391"></a>Derleyici Hatası C2391
'tanımlayıcısı': 'friend' tür tanımı sırasında kullanılamaz  
  
 `friend` Bildirimi tam sınıf bildirimi içerir. A `friend` bildirimi üye işlevi veya ayrıntılandırılmış tür belirteci, ancak tüm sınıf bildirimi belirtebilirsiniz.  
  
 Aşağıdaki örnek C2326 oluşturur:  
  
```  
// C2391.cpp  
// compile with: /c  
class D {   
   void func( int );   
};  
  
class A {  
   friend class B { int i; };   // C2391  
  
   // OK  
   friend class C;  
   friend void D::func(int);  
};  
```