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
ms.workload: cplusplus
ms.openlocfilehash: 344febd6b849667e108f06d69c773bb656b16f61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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