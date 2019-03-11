---
title: 'Nasıl yapılır: C++ birlikte çalışması kullanarak COM dizelerini sıralama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- COM [C++], marshaling strings
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
ms.openlocfilehash: baf3a2e6720cd2f72606cf5089e0409df602fee6
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751524"
---
# <a name="how-to-marshal-com-strings-using-c-interop"></a>Nasıl yapılır: C++ birlikte çalışması kullanarak COM dizelerini sıralama

Bu konuda bir BSTR (COM programlamasında stadyumlarda temel dize biçimi) nasıl olabileceğini gösterir. yönetilmeyen bir işleve, burada ayarladıklarınızı yönetilen bir işlevden geçirildi. Diğer dizeleri türleriyle çalışmak için aşağıdaki konulara bakın:

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak Unicode Dizelerini Hazırlama](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak ANSI Dizelerini Hazırlama](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

Aşağıdaki kod örnekleri kullan [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) #pragma yönergeleri uygulamak için yönetilen ve yönetilmeyen işlevleri aynı dosyada, ancak bu işlevler ayrı dosyalarında tanımlandıysa aynı şekilde birlikte çalışır. Yalnızca yönetilmeyen işlevleri içeren dosyalar ile derlenmesine gerek yoktur [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir BSTR (COM programlamada kullanılan bir dize biçimi) nasıl geçirilebilir gösterir. yönetilmeyen bir işleve bir yönetilen öğesinden. Arama Yönetilen işlev <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> .NET System.String içeriğini BSTR gösterimini adresini almak için. This işaretçisi kullanılarak sabitlenmiş [pin_ptr (C + +/ CLI)](../windows/pin-ptr-cpp-cli.md) yönetilmeyen işlev çalışırken fiziksel adresini bir çöp toplama döngüsü sırasında değiştirilmez emin olmak için. Çöp toplayıcı belleği kadar taşınmasını Yasaklanmış [pin_ptr (C + +/ CLI)](../windows/pin-ptr-cpp-cli.md) kapsam dışına gider.

```
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

## <a name="example"></a>Örnek

Aşağıdaki örnek, nasıl bir BSTR geçtiğini gösterir. yönetilmeyen bir işlev yönetilmeyen öğesinden. Yönetilen işlevi BSTR dizesini kullanabilir veya kullanın alma <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> öğesine dönüştürmek için bir <xref:System.String> diğer ile kullanmak için yönetilen işlevleri. BSTR temsil eden bellek yönetilmeyen yığında ayrılır, yönetilmeyen yığındaki çöp toplama olduğundan hiçbir Sabitleme gerekli olmasıdır.

```
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

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
