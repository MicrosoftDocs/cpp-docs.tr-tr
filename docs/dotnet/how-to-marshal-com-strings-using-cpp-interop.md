---
title: 'Nasıl yapılır: C++ Birlikte Çalışması Kullanarak COM Dizelerini Sıralama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- COM [C++], marshaling strings
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
ms.openlocfilehash: 3113f0bd04fc8433dc4c7f443914fca9245a54f4
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414340"
---
# <a name="how-to-marshal-com-strings-using-c-interop"></a>Nasıl yapılır: C++ Birlikte Çalışması Kullanarak COM Dizelerini Sıralama

Bu konuda, bir BSTR 'nin (COM programlamasında basit dize biçimi) yönetilen bir işlevden yönetilmeyen bir işleve nasıl geçirilebileceğini ve tam tersi gösterilmektedir. Diğer dizeler türleriyle birlikte çalışma için aşağıdaki konulara bakın:

- [Nasıl yapılır: C++ birlikte çalışabilirliği kullanarak Unicode dizelerini sıralama](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ birlikte çalışması kullanarak ANSI Dizelerini Sıralama](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

Aşağıdaki kod örnekleri, yönetilen ve yönetilmeyen işlevleri aynı dosyada uygulamak için [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) #pragma yönergelerini kullanır, ancak bu işlevler ayrı dosyalarda tanımlanmışsa aynı şekilde çalışır. Yalnızca yönetilmeyen işlevleri içeren dosyaların [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)ile derlenmesi gerekmez.

## <a name="example-pass-bstr-from-managed-to-unmanaged-function"></a>Örnek: istemciden yönetilmeyen işleve BSTR 'yi geçirin

Aşağıdaki örnek, bir BSTR 'nin (COM programlamasında kullanılan dize biçiminin) yönetilen bir işlevden yönetilmeyen bir işleve nasıl geçirilebileceğini gösterir. Çağıran yönetilen işlev, <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> bir .NET System. String IÇERIĞININ BSTR gösteriminin adresini almak için kullanır. Bu işaretçi, yönetilmeyen işlev yürütülürken bir çöp toplama çevrimi sırasında fiziksel adresinin değişmediğinden emin olmak için [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) kullanılarak sabitlenir. Çöp toplayıcısının, [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) kapsam dışına çıkana kadar belleği taşımasını yasaktır.

```cpp
// MarshalBSTR1.cpp
// compile with: /clr
#define WINVER 0x0502
#define _AFXDLL
#include <afxwin.h>

#include <iostream>
using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

void NativeTakesAString(BSTR bstr) {
   printf_s("%S", bstr);
}

#pragma managed

int main() {
   String^ s = "test string";

   IntPtr ip = Marshal::StringToBSTR(s);
   BSTR bs = static_cast<BSTR>(ip.ToPointer());
   pin_ptr<BSTR> b = &bs;

   NativeTakesAString( bs );
   Marshal::FreeBSTR(ip);
}
```

## <a name="example-pass-bstr-from-unmanaged-to-managed-function"></a>Örnek: yönetilmeyenden yönetilen işleve BSTR 'yi geçirin

Aşağıdaki örnek, bir BSTR 'nin yönetilmeyen bilgisayardan yönetilen bir işleve nasıl geçirilebileceğini göstermektedir. Alma yönetilen işlevi, içinde dizeyi bir BSTR veya <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> <xref:System.String> diğer yönetilen işlevlerle kullanmak üzere dönüştürmek için kullanabilir. BSTR 'yi temsil eden bellek yönetilmeyen yığında ayrıldığından, yönetilmeyen yığında çöp toplama olmadığından hiçbir sabitleme gerekmez.

```cpp
// MarshalBSTR2.cpp
// compile with: /clr
#define WINVER 0x0502
#define _AFXDLL
#include <afxwin.h>

#include <iostream>
using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed

void ManagedTakesAString(BSTR bstr) {
   String^ s = Marshal::PtrToStringBSTR(static_cast<IntPtr>(bstr));
   Console::WriteLine("(managed) convered BSTR to String: '{0}'", s);
}

#pragma unmanaged

void UnManagedFunc() {
   BSTR bs = SysAllocString(L"test string");
   printf_s("(unmanaged) passing BSTR to managed func...\n");
   ManagedTakesAString(bs);
}

#pragma managed

int main() {
   UnManagedFunc();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
