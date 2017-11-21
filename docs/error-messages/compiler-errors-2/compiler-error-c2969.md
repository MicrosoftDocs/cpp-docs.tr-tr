---
title: "Derleyici Hatası C2969 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2969
dev_langs: C++
helpviewer_keywords: C2969
ms.assetid: e4ea3d66-b937-4b2c-b42a-96e03fb11579
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fbb6606e3e0b6a007574dde7ec1f012cbb49a841
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2969"></a>Derleyici Hatası C2969
sözdizimi hatası: 'simgesi': beklenen ile sona erdirmek için üye işlev tanımının '}'  
  
 Bir şablon üye işlev tanımını eşleşmeyen kapanış ayracı sahiptir.  
  
 Aşağıdaki örnek C2969 oluşturur:  
  
```  
// C2969.cpp  
// compile with: /c  
class A {  
   int i;  
public:  
   A(int i) {}  
};  
  
A anA(1);  
  
class B {  
   A a;  
   B() : a(anA);   // C2969  
   // try the following line instead  
   // B() : a(anA) {}  
};  
```