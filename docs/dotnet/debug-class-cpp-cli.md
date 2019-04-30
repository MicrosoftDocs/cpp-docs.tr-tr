---
title: Hata Ayıklama Sınıfı (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
ms.openlocfilehash: 3a262a0d2ef429cb94f4648eb7c7180e7b130279
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393785"
---
# <a name="debug-class-ccli"></a>Hata Ayıklama Sınıfı (C++/CLI)

Kullanırken <xref:System.Diagnostics.Debug> bir Visual C++ uygulamasında hata ayıklama ve yayın derlemesi arasında davranışını değiştirmez.

## <a name="remarks"></a>Açıklamalar

Davranışını <xref:System.Diagnostics.Trace> hata ayıklama sınıfı davranışını aynıdır, ancak izleme tanımlanan sembol sunucusunda bağlıdır. Bu, gerektiğini anlamına gelir `#ifdef` derleme hata ayıklama davranışı önlemek için tüm izleme ile ilgili kod.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, her zaman ile derleme bağımsız olarak çıkış deyimleri yürütür **/DDEBUG** veya **/DTRACE**.

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

### <a name="output"></a>Çıkış

```Output
    Entering Main
Hello World.
    Exiting Main
test
```

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Beklenen davranış almak için (diğer bir deyişle, "test" çıkış yazdırılmış bir yayın yapısı için), kullanmanız gereken `#ifdef` ve `#endif` yönergeleri. Yukarıdaki örnek kod, aşağıda bu düzeltmeyi göstermek için değiştirilir:

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
