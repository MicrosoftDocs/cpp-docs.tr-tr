---
title: "Derleyici Hatası C3379 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3379
dev_langs: C++
helpviewer_keywords: C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e6fa111a525d81c418d3285c05af86b700e8cb08
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3379"></a>Derleyici Hatası C3379
'class': iç içe geçmiş sınıf bildiriminden bir parçası olarak bir derleme erişim belirticisi olamaz  
  
 Sınıfta veya yapı, gibi bir yönetilen türü uygulandığında [ortak](../../cpp/public-cpp.md) ve [özel](../../cpp/private-cpp.md) anahtar sözcükleri belirtmek sınıfı derleme meta verilerini kullanıma sunulan olup olmadığını. `public`veya `private` kapsayan sınıfının derleme erişimi devralır bir iç içe geçmiş sınıf uygulanamaz.  
  
 İle kullanıldığında [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), `ref` ve `value` anahtar sözcükleri gösteren bir sınıf yönetilir (bkz [sınıflar ve yapılar](../../windows/classes-and-structs-cpp-component-extensions.md)).  
  
 Aşağıdaki örnek C3379 oluşturur:  
  
```  
// C3379a.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class A {  
public:  
   static int i = 9;  
  
   public ref class BA {   // C3379  
   // try the following line instead  
   // ref class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A^ myA = gcnew A;  
   Console::WriteLine(myA->i);  
  
   A::BA^ myBA = gcnew A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```  
