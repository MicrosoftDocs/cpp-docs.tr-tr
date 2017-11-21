---
title: "Derleyici Hatası C3374 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3374
dev_langs: C++
helpviewer_keywords: C3374
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 16c857cf431462abd2acc21cf7444ec0aad2d075
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3374"></a>Derleyici Hatası C3374
'işlevinin' adresi temsilci örneği oluşturma sürece alınamıyor  
  
 Bir işlevin adresini temsilci örneğinin oluşturulmasını farklı bir bağlam yapılmadı.  
  
 Aşağıdaki örnek C3374 oluşturur:  
  
```  
// C3374.cpp  
// compile with: /clr  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      System::Console::WriteLine("in func1 {0}", i);  
   }  
};  
  
int main() {  
   &A::func1;   // C3374  
  
   // OK  
   A ^ a = gcnew A;  
   MyDel ^ StaticDelInst = gcnew MyDel(a, &A::func1);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: temsilcileri tanımlama ve kullanma (C + +/ CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)