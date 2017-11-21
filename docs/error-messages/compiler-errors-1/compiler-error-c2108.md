---
title: "Derleyici Hatası C2108 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2108
dev_langs: C++
helpviewer_keywords: C2108
ms.assetid: c84f0b47-5e2c-47d2-8edb-427a40e17c36
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 936c7f53ba112d2fc7bf03d76acac27bd8b4c372
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2108"></a>Derleyici Hatası C2108
alt simge Tamsayı türünde değil  
  
 Dizi alt simge işlemesinin ifadesidir.  
  
## <a name="example"></a>Örnek  
 C2108 yanlış kullanırsanız oluşabilir `this` işaretçi türünün varsayılan dizin oluşturucu erişmek için bir değer türü. Daha fazla bilgi için bkz: [bu semantiği işaretçi](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).  
  
 Aşağıdaki örnek C2108 oluşturur.  
  
```  
// C2108.cpp  
// compile with: /clr  
using namespace System;  
  
value struct B {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
   void Test() {  
      Console::WriteLine("{0}", this[3.3]);   // C2108  
      Console::WriteLine("{0}", this->default[3.3]);   // OK  
   }  
};  
  
int main() {  
   B ^ myb = gcnew B();  
   myb->Test();  
}  
```