---
description: 'Daha fazla bilgi edinin: hata ayıklama sınıfı (C++/CLı)'
title: Hata Ayıklama Sınıfı (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
ms.openlocfilehash: 255fe306684928faf836cd550005eea820d64ce5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258440"
---
# <a name="debug-class-ccli"></a>Hata Ayıklama Sınıfı (C++/CLI)

<xref:System.Diagnostics.Debug>Visual C++ uygulamasında kullanırken, davranış hata ayıklama ve yayın derlemesi arasında değişmez.

## <a name="remarks"></a>Açıklamalar

Davranışı <xref:System.Diagnostics.Trace> hata ayıklama sınıfının davranışıyla aynıdır, ancak tanımlanmakta olan sembol izlemesine bağımlıdır. Bu, `#ifdef` bir yayın derlemesinde hata ayıklama davranışını engellemek Için izlemeye ilişkin herhangi bir koda ihtiyacınız olduğu anlamına gelir.

## <a name="example-always-executes-output-statements"></a>Örnek: her zaman çıkış deyimlerini yürütür

### <a name="description"></a>Açıklama

Aşağıdaki örnek, **/DDEBUG** veya **/DTrace** ile derlemenize bakılmaksızın, her zaman output deyimlerini yürütür.

### <a name="code"></a>Kod

```cpp
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

### <a name="output"></a>Çıktı

```Output
    Entering Main
Hello World.
    Exiting Main
test
```

## <a name="example-use-ifdef-and-endif-directives"></a>Örnek: #ifdef ve #endif yönergelerini kullanın

### <a name="description"></a>Açıklama

Beklenen davranışı almak için (yani, bir yayın derlemesi için "test" çıkışı yazdırıldıysa) `#ifdef` ve yönergelerini kullanmanız gerekir `#endif` . Önceki kod örneği, bu düzeltmesini göstermek için aşağıda değiştirilmiştir:

### <a name="code"></a>Kod

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
