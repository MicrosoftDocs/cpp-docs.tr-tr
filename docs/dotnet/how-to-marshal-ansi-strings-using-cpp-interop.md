---
title: 'Nasıl yapılır: C++ Birlikte Çalışması Kullanarak ANSI Dizelerini Sıralama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- ANSI [C++], marshaling strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
ms.assetid: 5eda2eb6-5140-40f0-82cf-7ce171fffb45
ms.openlocfilehash: 6987b23311354cfe6fd095e0e811d043e9b9692e
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988470"
---
# <a name="how-to-marshal-ansi-strings-using-c-interop"></a>Nasıl yapılır: C++ Birlikte Çalışması Kullanarak ANSI Dizelerini Sıralama

Bu konu, ANSI dizelerinin birlikte çalışabilirlik kullanılarak C++ nasıl geçirileceğini gösterir ancak .NET Framework <xref:System.String> dizeleri Unicode biçiminde temsil eder, bu nedenle ANSI 'ye dönüştürme ek bir adımdır. Diğer dize türleriyle birlikte çalışma için aşağıdaki konulara bakın:

- [Nasıl yapılır: C++ Çalışabilirliği Kullanarak Unicode Dizelerini Sıralama](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak COM Dizelerini Sıralama](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

Aşağıdaki kod örnekleri, yönetilen ve yönetilmeyen işlevleri aynı dosyada uygulamak için [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) #pragma yönergelerini kullanır, ancak bu işlevler ayrı dosyalarda tanımlanmışsa aynı şekilde çalışır. Yalnızca yönetilmeyen işlevleri içeren dosyaların [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)ile derlenmesi gerekli olmadığından, bunların performans özelliklerini koruyabilir.

## <a name="example"></a>Örnek

Örnek, <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A>kullanılarak yönetilmeyen bir işleve bir ANSI dizesinin geçtiğini gösterir. Bu yöntem, yönetilmeyen yığında bellek ayırır ve dönüştürme gerçekleştirildikten sonra adresi döndürür. Bu, hiçbir sabitleme gerekmediği anlamına gelir (GC yığınındaki bellek, yönetilmeyen işleve geçirilmediğinden) ve <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> tarafından döndürülen IntPtr 'ın açık olarak bırakılması veya bir bellek sızıntısı sonuçları olması gerekir.

```cpp
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

Aşağıdaki örnek, yönetilmeyen bir işlev tarafından çağrılan yönetilen bir işlevde bir ANSI dizesine erişmek için gereken veri sıralamasını gösterir. Yerel dizeyi alma sırasında yönetilen işlev doğrudan kullanabilir veya gösterildiği gibi <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> yöntemi kullanılarak yönetilen bir dizeye dönüştürebilir.

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
