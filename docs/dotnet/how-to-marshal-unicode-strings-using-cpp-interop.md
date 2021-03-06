---
description: 'Daha fazla bilgi edinin: nasıl yapılır: C++ birlikte çalışabilirliği kullanarak Unicode dizelerini sıralama'
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
ms.openlocfilehash: 7aa21acc912aafec7d3fccd78f7e9f1ab216ea86
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302523"
---
# <a name="how-to-marshal-unicode-strings-using-c-interop"></a>Nasıl yapılır: C++ Çalışabilirliği Kullanarak Unicode Dizelerini Sıralama

Bu konuda Visual C++ birlikte çalışabilirliğinin bir modeli gösterilmektedir. Daha fazla bilgi için bkz. [C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

Aşağıdaki kod örnekleri, yönetilen ve yönetilmeyen işlevleri aynı dosyada uygulamak için [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) #pragma yönergelerini kullanır, ancak bu işlevler ayrı dosyalarda tanımlanmışsa aynı şekilde çalışır. Yalnızca yönetilmeyen işlevleri içeren dosyaların [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)ile derlenmesi gerekmez.

Bu konu, Unicode dizelerinin yönetilen bir işlevden yönetilmeyen bir işleve nasıl geçirilebileceğini ve bunun tersini gösterir. Diğer dizeler türleriyle birlikte çalışma için aşağıdaki konulara bakın:

- [Nasıl yapılır: C++ birlikte çalışması kullanarak ANSI Dizelerini Sıralama](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ birlikte çalışması kullanarak COM dizelerini sıralama](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

## <a name="example-pass-unicode-string-from-managed-to-unmanaged-function"></a>Örnek: yönetilen 'ten yönetilmeyen işleve Unicode dize geçirin

Yönetilen bir istemciden yönetilmeyen bir işleve Unicode dizesi geçirmek için, yönetilen dizenin depolandığı belleğe erişmek üzere PtrToStringChars işlevi (Vcclr. h içinde bildirilmiştir) kullanılabilir. Bu adres yerel bir işleve geçirilecek olduğundan, dize verilerinin yeniden konumlandırılmasını engellemek için belleğin [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) ile sabitlenebileceğinden, yönetilmeyen işlev yürütülürken çöp toplama döngüsünün gerçekleşmesi gerekir.

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

## <a name="example-data-marshaling-required-to-access-unicode-string"></a>Örnek: Unicode dizesine erişmek için veri hazırlama gerekir

Aşağıdaki örnek, yönetilmeyen bir işlev tarafından çağrılan yönetilen bir işlevde Unicode dizesine erişmek için gereken veri hazırlamayı gösterir. Yönetilen işlev, yerel Unicode dizesini alırken, yöntemi kullanılarak yönetilen bir dizeye dönüştürür <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> .

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

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
