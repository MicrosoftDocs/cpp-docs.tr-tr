---
title: 'Nasıl yapılır: C++ Çalışabilirliği kullanarak Unicode dizelerini sıralama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- Unicode, marshaling strings
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
ms.openlocfilehash: 37b56834e000cff686557730252f3d425f642772
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400558"
---
# <a name="how-to-marshal-unicode-strings-using-c-interop"></a>Nasıl yapılır: C++ Çalışabilirliği kullanarak Unicode dizelerini sıralama

Bu konuda, Visual C++ birlikte çalışabilirliği bir modeli gösterilmektedir. Daha fazla bilgi için [C++ Çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

Aşağıdaki kod örnekleri kullan [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) #pragma yönergeleri uygulamak için yönetilen ve yönetilmeyen işlevleri aynı dosyada, ancak bu işlevler ayrı dosyalarında tanımlandıysa aynı şekilde birlikte çalışır. Yalnızca yönetilmeyen işlevleri içeren dosyalar ile derlenmesine gerek yoktur [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).

Bu konu, Unicode dizelerini nasıl olabileceğini gösterir yönetilen bir işlevden geçirilen yönetilmeyen bir işleve ve bunun tersi de geçerlidir. Diğer dizeleri türleriyle çalışmak için aşağıdaki konulara bakın:

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak ANSI Dizelerini Hazırlama](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak COM Dizelerini Hazırlama](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

## <a name="example"></a>Örnek

(Vcclr.h içinde bildirilen) PtrToStringChars işlevi yönetilmeyen bir işleve bir Unicode dize yönetilen bir işlevden geçirmek için kullanılabilir yönetilen dize depolandığı bellekteki erişim için. Bu adresi bir yerel işleve geçirilir, bellek ile sabitlenmiş önemlidir, çünkü [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md) string veri taşınmasını önlemek için atık toplama döngüsü sırasında gerçekleşmesi gereken Yönetilmeyen işlevi yürütür.

```
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

Aşağıdaki örnek, yönetilmeyen bir işlev tarafından çağırılan yönetilen bir işlevdeki bir Unicode dize erişmek için gerekli veri hazırlamayı gösterir. Yerel Unicode dizesi alırken yönetilen işlevini kullanarak bir yönetilen dize dönüştürür <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> yöntemi.

```
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
