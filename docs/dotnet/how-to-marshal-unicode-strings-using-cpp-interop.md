---
title: 'Nasıl yapılır: C++ Çalışabilirliği Kullanarak Unicode Dizelerini Sıralama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- Unicode, marshaling strings
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
ms.openlocfilehash: f666e52b604e4713f02cb14744ac12a0407366a3
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988168"
---
# <a name="how-to-marshal-unicode-strings-using-c-interop"></a>Nasıl yapılır: C++ Çalışabilirliği Kullanarak Unicode Dizelerini Sıralama

Bu konuda, Visual C++ birlikte çalışabilirlik 'nin bir modeli gösterilmektedir. Daha fazla bilgi için bkz [. C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

Aşağıdaki kod örnekleri, yönetilen ve yönetilmeyen işlevleri aynı dosyada uygulamak için [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) #pragma yönergelerini kullanır, ancak bu işlevler ayrı dosyalarda tanımlanmışsa aynı şekilde çalışır. Yalnızca yönetilmeyen işlevleri içeren dosyaların [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)ile derlenmesi gerekmez.

Bu konu, Unicode dizelerinin yönetilen bir işlevden yönetilmeyen bir işleve nasıl geçirilebileceğini ve bunun tersini gösterir. Diğer dizeler türleriyle birlikte çalışma için aşağıdaki konulara bakın:

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak ANSI Dizelerini Sıralama](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak COM Dizelerini Sıralama](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

## <a name="example"></a>Örnek

Yönetilen bir istemciden yönetilmeyen bir işleve Unicode dizesi geçirmek için, yönetilen dizenin depolandığı belleğe erişmek üzere PtrToStringChars işlevi (Vcclr. h içinde bildirilmiştir) kullanılabilir. Bu adres yerel bir işleve geçirilecek olduğundan, dize verilerinin yeniden konumlandırılmasını engellemek için belleğin [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) sabitlendiği önemlidir, yönetilmeyen işlev yürütülürken çöp toplama döngüsünün gerçekleşmesi gerekir.

```cpp
// MarshalUnicode1.cpp
// compile with: /clr
#include <iostream>
#include <stdio.h>
#include <vcclr.h>

using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

void NativeTakesAString(const wchar_t* p) {
   printf_s("(native) received '%S'\n", p);
}

#pragma managed

int main() {
   String^ s = gcnew String("test string");
   pin_ptr<const wchar_t> str = PtrToStringChars(s);

   Console::WriteLine("(managed) passing string to native func...");
   NativeTakesAString( str );
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, yönetilmeyen bir işlev tarafından çağrılan yönetilen bir işlevde Unicode dizesine erişmek için gereken veri hazırlamayı gösterir. Yerel Unicode dizesini alırken yönetilen işlev, <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> yöntemini kullanarak yönetilen bir dizeye dönüştürür.

```cpp
// MarshalUnicode2.cpp
// compile with: /clr
#include <iostream>

using namespace std;
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed

void ManagedStringFunc(wchar_t* s) {
   String^ ms = Marshal::PtrToStringUni((IntPtr)s);
   Console::WriteLine("(managed) received '{0}'", ms);
}

#pragma unmanaged

void NativeProvidesAString() {
   cout << "(unmanaged) calling managed func...\n";
   ManagedStringFunc(L"test string");
}

#pragma managed

int main() {
   NativeProvidesAString();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
