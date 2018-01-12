---
title: "Derleyici Hatası C2252 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2252
dev_langs: C++
helpviewer_keywords: C2252
ms.assetid: fee74ab9-1997-4615-82fe-e6d1fe3aacd9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 60326d37e4c672487161abc53bf649056a2c4a52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2252"></a>Derleyici Hatası C2252
Geçerli kapsam şablonda açıkça örneği oluşturulamıyor  
  
 Derleyici bir açık örnekleme şablonu ile ilgili bir sorun algıladı.  Örneğin, bir işlev bir şablonda açıkça örneği oluşturulamıyor.  
  
 Aşağıdaki örnek C2252 oluşturur:  
  
```  
// C2252.cpp  
class A {  
public:  
   template <class T>  
   int getit(int i , T * it ) {  
      return i;  
   }  
   template int A::getit<double>(int i, double * it);   // C2252  
   // try the following line instead  
   // template <> int A::getit<double>(int i, double * it);  
  
};  
  
int main() {  
   // cannot explicitly instantiate in function  
   template int A::getit<long>(int i, long * it);   // C2252  
}  
```