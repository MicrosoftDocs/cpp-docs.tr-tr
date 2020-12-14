---
description: 'Daha fazla bilgi edinin: nasıl yapılır: C++ birlikte çalışması kullanarak ANSI Dizelerini Sıralama'
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
ms.openlocfilehash: 7a06e045c3c097cb866c6d289ce24638a6965d1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258271"
---
# <a name="how-to-marshal-ansi-strings-using-c-interop"></a>Nasıl yapılır: C++ Birlikte Çalışması Kullanarak ANSI Dizelerini Sıralama

Bu konuda, ANSI dizelerinin C++ birlikte çalışması kullanılarak nasıl geçirilebileceğini, ancak .NET Framework <xref:System.String> Unicode biçiminde dizeleri temsil ettiğinden, ANSI 'ye dönüştürme işlemi fazladan bir adımdır. Diğer dize türleriyle birlikte çalışma için aşağıdaki konulara bakın:

- [Nasıl yapılır: C++ birlikte çalışabilirliği kullanarak Unicode dizelerini sıralama](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ birlikte çalışması kullanarak COM dizelerini sıralama](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

Aşağıdaki kod örnekleri, yönetilen ve yönetilmeyen işlevleri aynı dosyada uygulamak için [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) #pragma yönergelerini kullanır, ancak bu işlevler ayrı dosyalarda tanımlanmışsa aynı şekilde çalışır. Yalnızca yönetilmeyen işlevleri içeren dosyaların [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)ile derlenmesi gerekli olmadığından, bunların performans özelliklerini koruyabilir.

## <a name="example-pass-ansi-string"></a>Örnek: Pass ANSI String

Örnek, kullanılarak yönetilmeyen bir işleve bir ANSI dizesinin geçtiğini gösterir <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> . Bu yöntem, yönetilmeyen yığında bellek ayırır ve dönüştürme gerçekleştirildikten sonra adresi döndürür. Bu, hiçbir sabitleme gerekmediği anlamına gelir (GC yığınındaki bellek yönetilmeyen işleve geçirilmediğinden) ve öğesinden döndürülen IntPtr 'ın <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> açıkça serbest bırakılması veya bellek sızıntısı sonuçları olması gerekir.

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

## <a name="example-data-marshaling-required-to-access-ansi-string"></a>Örnek: ANSI dizesine erişmek için veri hazırlama gerekiyor

Aşağıdaki örnek, yönetilmeyen bir işlev tarafından çağrılan yönetilen bir işlevde bir ANSI dizesine erişmek için gereken veri sıralamasını gösterir. Yerel dizeyi alma sırasında yönetilen işlev doğrudan kullanabilir ya da gösterildiği gibi yöntemini kullanarak yönetilen bir dizeye dönüştürebilirsiniz <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> .

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

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
