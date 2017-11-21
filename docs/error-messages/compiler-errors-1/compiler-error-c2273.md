---
title: "Derleyici Hatası C2273 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2273
dev_langs: C++
helpviewer_keywords: C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 58f7f13303b9941cf07e90685d68d7114213ea2d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2273"></a>Derleyici Hatası C2273
'type': '->' işlecinin sağ tarafında olarak geçersiz  
  
 Bir türü sağ işleneni, görünür bir `->` işleci.  
  
 Kullanıcı tanımlı tür dönüştürme erişmeye tarafından bu hataya neden. Anahtar sözcüğü kullanmak `operator` arasında -> ve `type`.  
  
 Aşağıdaki örnek C2273 oluşturur:  
  
```  
// C2273.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
int main() {  
   MyClass * ClassPtr = new MyClass;  
   int i = ClassPtr->int();   // C2273  
   int j = ClassPtr-> operator int();   // OK  
}  
```