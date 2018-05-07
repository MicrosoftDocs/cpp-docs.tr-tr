---
title: Derleyici Hatası C2550 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2550
dev_langs:
- C++
helpviewer_keywords:
- C2550
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d215f708513fd7313e0ff82f5b8853b1e00835af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2550"></a>Derleyici Hatası C2550
'tanımlayıcısı': oluşturucu başlatıcı listeleri Oluşturucusu tanımları izin verilmez  
  
 Bir temel sınıf başlatıcı listesi bir oluşturucu olmayan bir işlev tanımı kullanılır.  
  
 Aşağıdaki örnek C2550 oluşturur:  
  
```  
// C2550.cpp  
// compile with: /c  
class C {  
public:  
   C();  
};  
  
class D : public C {  
public:  
   D();  
   void func();  
};  
  
void D::func() : C() {}  // C2550  
D::D() : C() {}   // OK  
```