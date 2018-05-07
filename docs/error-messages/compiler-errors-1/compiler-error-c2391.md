---
title: Derleyici Hatası C2391 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2391
dev_langs:
- C++
helpviewer_keywords:
- C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a16ed19f5cac9d6c23a3f709e40fc290223e93c7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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