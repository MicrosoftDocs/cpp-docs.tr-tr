---
title: Derleyici Hatası C2553 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2553
dev_langs:
- C++
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8cfb09f2701b418ab5570641a78c465ff72ed943
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2553"></a>Derleyici Hatası C2553
'base_function': sanal işlevi geçersiz kılma dönüş türü 'override_function' farklıdır  
  
 Bir taban sınıf içinde sanal işlevi geçersiz kılmak türetilmiş bir sınıf işlevinde çalıştı, ancak türetilmiş sınıf işlevi temel sınıf işlevi aynı dönüş türüne sahip değildi.  Bir geçersiz kılma işlev imzası geçersiz kılıp işlev imzası eşleşmesi gerekir.  
  
 Aşağıdaki örnek C2553 oluşturur:  
  
```  
// C2553.cpp  
// compile with: /clr /c  
ref struct C {  
   virtual void f();  
};  
  
ref struct D : C {  
   virtual int f() override ;   // C2553   
  
   // try the following line instead  
   // virtual void f() override;  
};  
```