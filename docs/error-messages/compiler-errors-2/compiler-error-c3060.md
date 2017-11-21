---
title: "Derleyici Hatası C3060 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3060
dev_langs: C++
helpviewer_keywords: C3060
ms.assetid: 6282bb92-0546-4b59-9435-d3840bf93bdb
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 528ce6f8b94d73acde2a92412c6f3578dd83b4bd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3060"></a>Derleyici Hatası C3060
'member': arkadaş işlevi (bunu yalnızca bildirilebilir) bir tam ad kullanmayı bir sınıf içinde tanımlanmamış  
  
 Arkadaş işlevi izin verilmediğinden bir tam ad kullanmayı tanımlandı.  
  
 Aşağıdaki örnek C3060 oluşturur:  
  
```  
// C3060.cpp  
class A {  
public:  
   void func();  
};  
  
class C {  
public:  
   friend void A::func() { }   // C3060  
   // Try the following line and the out of class definition:  
   // friend void A::func();  
};  
  
// void A::func(){}  
```