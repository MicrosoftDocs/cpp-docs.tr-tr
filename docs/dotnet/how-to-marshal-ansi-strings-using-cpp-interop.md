---
title: 'Nasıl yapılır: C++ birlikte çalışması kullanarak ANSI dizelerini sıralama | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], strings
- ANSI [C++], marshaling strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
ms.assetid: 5eda2eb6-5140-40f0-82cf-7ce171fffb45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d4a1a0cd8b9da5812e404f70dc999dfaf1606666
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383369"
---
# <a name="how-to-marshal-ansi-strings-using-c-interop"></a>Nasıl yapılır: C++ Birlikte Çalışması Kullanarak ANSI Dizelerini Sıralama

Bu konu, ANSI dizelerini nasıl olabileceğini gösterir C++ birlikte çalışması ancak .NET Framework kullanarak geçirilen <xref:System.String> ANSI dönüştürme fazladan bir adım, bu nedenle Unicode biçiminde dizeleri temsil eder. Diğer dize türlerine ile çalışmak için aşağıdaki konulara bakın:

- [Nasıl yapılır: C++ Çalışabilirliği Kullanarak Unicode Dizelerini Sıralama](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak COM Dizelerini Sıralama](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

Aşağıdaki kod örnekleri kullan [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) #pragma yönergeleri uygulamak için yönetilen ve yönetilmeyen işlevleri aynı dosyada, ancak bu işlevler ayrı dosyalarında tanımlandıysa aynı şekilde birlikte çalışır. Yalnızca yönetilmeyen işlevleri içeren dosyalar ile derlenmesine gerek yoktur çünkü [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md), kendi performans özellikleri korurlar.

## <a name="example"></a>Örnek

Örnek, bir yönetilmeyen işlevi kullanarak bir ANSI dizesine yönetilen bir işlevden geçirmeyi gösterir <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A>. Bu yöntem, yönetilmeyen yığında bellek ayırır ve dönüştürme işlemini gerçekleştirdikten sonra adresini döndürür. Yani hiçbir sabitleme (bellek GC yığınındaki yönetilmeyen işleve geçirilir değil çünkü) gerekli olduğunu ve IntPtr öğesinden döndürülen <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> açıkça serbest bırakılması gerekir veya bellek sızıntısı.

```
// MarshalANSI1.cpp
// compile with: /clr
#include <iostream>
#include <stdio.h>

using namespace std;
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

void NativeTakesAString(const char* p) {
   printf_s("(native) received '%s'\n", p);
}

#pragma managed

int main() {
   String^ s = gcnew String("sample string");
   IntPtr ip = Marshal::StringToHGlobalAnsi(s);
   const char* str = static_cast<const char*>(ip.ToPointer());

   Console::WriteLine("(managed) passing string...");
   NativeTakesAString( str );

   Marshal::FreeHGlobal( ip );
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, yönetilmeyen bir işlev tarafından çağrılan yönetilen bir işlevdeki bir ANSI dizesine erişmek için gerekli veri hazırlamayı gösterir. Yerel dize Yönetilen işlev alırken doğrudan kullanabilir veya onu kullanarak bir yönetilen dize dönüştürme <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> gösterildiği yöntemi.

```
// MarshalANSI2.cpp
// compile with: /clr
#include <iostream>
#include <vcclr.h>

using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed

void ManagedStringFunc(char* s) {
   String^ ms = Marshal::PtrToStringAnsi(static_cast<IntPtr>(s));
   Console::WriteLine("(managed): received '{0}'", ms);
}

#pragma unmanaged

void NativeProvidesAString() {
   cout << "(native) calling managed func...\n";
   ManagedStringFunc("test string");
}

#pragma managed

int main() {
   NativeProvidesAString();
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)