---
title: "Derleyici Hatası C2875 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2875
dev_langs: C++
helpviewer_keywords: C2875
ms.assetid: d589fc0c-08b2-4a79-bc0e-dca5eb80bdd5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e4a6a509bd445b5d3acda538e92d5d4c6b42a6f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2875"></a>Derleyici Hatası C2875
using bildirimi 'class::identifier' birden çok bildirimini neden olur.  
  
 Bildirim iki kez tanımlanması için aynı öğeyi neden olur.  
  
 Aşağıdaki örnek C2875 oluşturur:  
  
```  
// C2875.cpp  
struct A {  
   void f(int*);  
};  
  
struct B {  
   void f(double*);  
};  
  
struct AB : A, B {  
   using A::f;  
   using A::f;   // C2875  
   using B::f;  
};  
```