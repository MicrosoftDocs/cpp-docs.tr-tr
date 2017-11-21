---
title: "Derleyici Hatası C2683 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2683
dev_langs: C++
helpviewer_keywords: C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b3e79c1a05ac0d1fab713e2dfa97c9da740088bb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2683"></a>Derleyici Hatası C2683
'cast': 'type' tür çok biçimli bir tür değil  
  
 Kullanamazsınız [dynamic_cast](../../cpp/dynamic-cast-operator.md) biçimli olmayan bir sınıftan (hiçbir sanal işlevler sınıfıyla) dönüştürmek için.  
  
 Kullanabileceğiniz [static_cast](../../cpp/static-cast-operator.md) biçimli olmayan türleri dönüştürme gerçekleştirmek için. Ancak, `static_cast` bir çalışma zamanı denetimi gerçekleştirmez.  
  
 Aşağıdaki örnek C2683 oluşturur:  
  
```  
// C2683.cpp  
// compile with: /c  
class B { };  
class D : public B { };  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  // C2683  
   D* pd1 = static_cast<D*>(pb);   // OK  
}  
```