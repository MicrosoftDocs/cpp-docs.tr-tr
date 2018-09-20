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
ms.openlocfilehash: eecda10f2fd88b902a54fe9f4dc4de8edc4bc1b0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413568"
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

## <a name="see-also"></a>Ayrıca Bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)