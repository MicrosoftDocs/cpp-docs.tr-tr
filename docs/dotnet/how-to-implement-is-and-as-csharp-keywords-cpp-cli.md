---
title: 'Nasıl yapılır: uygulama olduğundan ve as C# anahtar sözcüklerini uygulama (C + +/ CLI) | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- as C# keyword [C++]
- is C# keyword [C++]
ms.assetid: bc66c0d1-696b-480d-977c-5d9d1ad1ece6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 30396b803d295c978446707a87cc8bf098d701bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
 [Diğer .NET Dilleri ile Birlikte Çalışabilirlik (C++/CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)