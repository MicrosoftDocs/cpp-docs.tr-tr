---
title: "Derleyici Hatası C2681 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2681
dev_langs: C++
helpviewer_keywords: C2681
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9978a520b4682e4e2c7c4856d4e42675be0ab901
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2681"></a>Derleyici Hatası C2681
'type': adı için geçersiz bir ifade türü  
  
 Geçersiz bir türünden dönüştürmek bir atama işleci çalıştı. Örneğin, kullanırsanız [dynamic_cast](../../cpp/dynamic-cast-operator.md) kaynağı deyim, bir işaretçi türü bir ifadeyi dönüştürmek için işleci bir işaretçi olması gerekir.  
  
 Aşağıdaki örnek C2681 oluşturur:  
  
```  
// C2681.cpp  
class A { virtual void f(); };  
  
void g(int i) {  
    A* pa;  
    pa = dynamic_cast<A*>(i);  // C2681  
}  
```