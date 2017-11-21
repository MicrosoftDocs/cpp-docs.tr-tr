---
title: "Derleyici Hatası C2885 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2885
dev_langs: C++
helpviewer_keywords: C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a19f209d53d7d0b37cddbf559fa3dc02ee50db7e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2885"></a>Derleyici Hatası C2885
'class::identifier': olmayan bir geçerli using bildirimi sınıfı olmayan kapsamda  
  
 Kullanılan bir [kullanarak](../../cpp/using-declaration.md) bildirimi hatalı.  
  
## <a name="example"></a>Örnek  
 Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucunda oluşturulabilir: artık sahip için geçerli olan bir `using` iç içe geçmiş tür; bildirimine türü bir ad put iç içe geçmiş tür için yaptığınız her başvuru açıkça nitelemeniz gerekir boşluk veya bir typedef oluşturun.  
  
 Aşağıdaki örnek C2885 oluşturur.  
  
```  
// C2885.cpp  
namespace MyNamespace {  
   class X1 {};  
}  
  
struct MyStruct {  
   struct X1 {  
      int i;  
   };  
};  
  
int main () {  
   using MyStruct::X1;   // C2885  
  
   // OK  
   using MyNamespace::X1;  
   X1 myX1;  
  
   MyStruct::X1 X12;  
  
   typedef MyStruct::X1 abc;  
   abc X13;  
   X13.i = 9;  
}  
```  
  
## <a name="example"></a>Örnek  
 Kullanırsanız `using` C++ bir sınıf üyesi olan anahtar sözcük başka bir sınıf (türetilmiş bir sınıf) içinde bu üye tanımlamanızı gerektirir.  
  
 Aşağıdaki örnek C2885 oluşturur.  
  
```  
// C2885_b.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
};  
  
void z() {  
   using A::i;   // C2885 not in a class  
}  
  
class B : public A {  
public:  
   using A::i;  
};  
```