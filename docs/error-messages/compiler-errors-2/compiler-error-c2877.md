---
title: Derleyici Hatası C2877 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2877
dev_langs:
- C++
helpviewer_keywords:
- C2877
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96ab91d64806e7d4ca28bf43e812640790b78e87
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2877"></a>Derleyici Hatası C2877
'simgesi' 'sınıfından' erişilebilir değil  
  
 Bir taban sınıftan türetilen tüm üyeleri türetilen sınıfta erişilebilir olması gerekir.  
  
 Aşağıdaki örnek C2877 oluşturur:  
  
```  
// C2877.cpp  
// compile with: /c  
class A {  
private:  
   int a;  
};  
  
class B : public A {  
   using A::a;   // C2877  
};  
```