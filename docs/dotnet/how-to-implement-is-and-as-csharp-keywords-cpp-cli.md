---
title: "Nasıl yapılır: uygulama olduğundan ve as C# anahtar sözcüklerini uygulama (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- as C# keyword [C++]
- is C# keyword [C++]
ms.assetid: bc66c0d1-696b-480d-977c-5d9d1ad1ece6
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ae9753a30e513a237d658e3110b9174072ccd25b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-implement-is-and-as-c-keywords-ccli"></a>Nasıl yapılır: is ve as C# Anahtar Sözcüklerini Uygulama (C++/CLI)
Bu konuda işlevselliğini uygulamak nasıl gösterilmektedir `is` ve `as` Visual c++ C# anahtar sözcükleri.  
  
## <a name="example"></a>Örnek  
  
```  
// CS_is_as.cpp  
// compile with: /clr  
using namespace System;  
  
interface class I {  
public:  
   void F();  
};  
  
ref struct C : public I {  
   virtual void F( void ) { }  
};  
  
template < class T, class U >   
Boolean isinst(U u) {  
   return dynamic_cast< T >(u) != nullptr;  
}  
  
int main() {  
   C ^ c = gcnew C();  
   I ^ i = safe_cast< I ^ >(c);   // is (maps to castclass in IL)  
   I ^ ii = dynamic_cast< I ^ >(c);   // as (maps to isinst in IL)  
  
   // simulate 'as':  
   Object ^ o = "f";  
   if ( isinst< String ^ >(o) )  
      Console::WriteLine("o is a string");  
}  
```  
  
```Output  
o is a string  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Diğer .NET dilleri ile birlikte çalışabilirlik (C + +/ CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)