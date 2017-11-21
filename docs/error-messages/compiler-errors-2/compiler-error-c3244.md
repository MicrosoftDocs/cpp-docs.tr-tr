---
title: "Derleyici Hatası C3244 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3244
dev_langs: C++
helpviewer_keywords: C3244
ms.assetid: dae6c49b-5212-4206-8f61-d4010c0b9969
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 225b3e95e2f0ba7e41959732f2c11b8860ef8b3b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3244"></a>Derleyici Hatası C3244
'yöntemi': 'arabirimi' göre değil 'arabirimi' tarafından sunulan bu yöntemi  
  
 Çalıştığınız [açıkça geçersiz](../../cpp/explicit-overrides-cpp.md) belirtilen arabiriminde yok ancak başka bir taban sınıf içinde mevcut üyesi.  
  
 Aşağıdaki örnek C3244 oluşturur:  
  
```  
// C3244.cpp  
#pragma warning(disable:4199)  
  
__interface IX15A {  
   void f();  
};  
  
__interface IX15B {  
   void g();  
};  
  
class CX15 : public IX15A, public IX15B {  
public:        
   void IX15A::f();  
   void IX15B::g();  
};  
  
void CX15::IX15A::g()   // C3244 occurs here  
{  
}  
```