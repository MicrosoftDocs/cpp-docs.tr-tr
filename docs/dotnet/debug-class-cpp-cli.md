---
title: "Hata ayıklama sınıfı (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 14354241c4e16e1177a5680b901a738f16036f96
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="debug-class-ccli"></a>Hata Ayıklama Sınıfı (C++/CLI)
Kullanırken <xref:System.Diagnostics.Debug> bir Visual C++ uygulamasında davranışı bir hata ayıklama ve yayın derlemesi arasında değiştirmez.  
  
## <a name="remarks"></a>Açıklamalar  
 Davranışını <xref:System.Diagnostics.Trace> hata ayıklama sınıfı için davranış aynıdır, ancak tanımlanmakta izleme simgesinin üzerine bağlıdır. Bu, gerektiği anlamına gelir `#ifdef` yayın derlemesinde hata ayıklama davranışı önlemek için izleme ile ilgili kod.  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek çıkış deyimlerini ile derleme bağımsız olarak her zaman yürütür **/DDEBUG** veya **/DTRACE**.  
  
### <a name="code"></a>Kod  
  
```  
// mcpp_debug_class.cpp  
// compile with: /clr  
#using <system.dll>  
using namespace System::Diagnostics;  
using namespace System;  
  
int main() {  
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );  
   Trace::AutoFlush = true;  
   Trace::Indent();  
   Trace::WriteLine( "Entering Main" );  
   Console::WriteLine( "Hello World." );  
   Trace::WriteLine( "Exiting Main" );  
   Trace::Unindent();  
  
   Debug::WriteLine("test");  
}  
```  
  
### <a name="output"></a>Çıkış  
  
```  
    Entering Main  
Hello World.  
    Exiting Main  
test  
```  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Beklenen davranışı elde etmek üzere (diğer bir deyişle, "test" çıktı yazdırılan yayın derlemesi için), kullanmalısınız `#ifdef` ve `#endif` yönergeleri. Yukarıdaki örnek kod, bu düzeltmenin göstermek için aşağıda değiştirilir:  
  
### <a name="code"></a>Kod  
  
```  
// mcpp_debug_class2.cpp  
// compile with: /clr  
#using <system.dll>  
using namespace System::Diagnostics;  
using namespace System;  
  
int main() {  
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );  
   Trace::AutoFlush = true;  
   Trace::Indent();  
  
#ifdef TRACE   // checks for a debug build  
   Trace::WriteLine( "Entering Main" );  
   Console::WriteLine( "Hello World." );  
   Trace::WriteLine( "Exiting Main" );  
#endif  
   Trace::Unindent();  
  
#ifdef DEBUG   // checks for a debug build  
   Debug::WriteLine("test");  
#endif   //ends the conditional block  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)