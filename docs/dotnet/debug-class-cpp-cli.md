---
title: Hata ayıklama sınıfı (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fddf192b21b878c82ca663da657c55e32fd9173d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106212"
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
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)