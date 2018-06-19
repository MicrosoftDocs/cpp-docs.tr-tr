---
title: 'Nasıl yapılır: C++ Çalışabilirliği kullanarak Unicode dizelerini sıralama | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- Unicode, marshaling strings
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e5290958a55c61dd55adac0f182af7163896d694
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130470"
---
# <a name="how-to-marshal-unicode-strings-using-c-interop"></a>Nasıl yapılır: C++ Çalışabilirliği Kullanarak Unicode Dizelerini Sıralama
Bu konuda, bir model Visual C++ birlikte çalışabilirlik gösterilir. Daha fazla bilgi için bkz: [C++ Çalışabilirliği kullanarak (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 Aşağıdaki kod örnekleri kullan [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) uygulamak için #pragma yönergeleri yönetilen ve yönetilmeyen işlevleri aynı dosyada, ancak bu işlevler ayrı dosyalarda tanımlanırsa aynı şekilde birlikte çalışır. Yalnızca yönetilmeyen işlevleri içeren dosyalar ile derlenmesi gerekmez [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Bu konuda nasıl Unicode dizeleri gösterilmektedir yönetilmeyen bir işleve ve tersi yönde yönetilen işlevden geçirildi. Diğer dizeler türleriyle birlikte çalışmak için aşağıdaki konulara bakın:  
  
-   [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak ANSI Dizelerini Sıralama](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
-   [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak COM Dizelerini Sıralama](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
## <a name="example"></a>Örnek  
 (Vcclr.h'de belirtilmiş) PtrToStringChars işlevi bir UNICODE dizesi yönetilmeyen bir işleve yönetilen işlevden geçirmek için kullanılabilir yönetilen dize depolandığı bellekte erişmek için. Bu adres için yerel bir işleve geçirilir, bellek ile sabitlenmelidir önemlidir, çünkü [pin_ptr (C + +/ CLI)](../windows/pin-ptr-cpp-cli.md) dize verilerin taşınmasını engellemek için bir atık toplama döngüsü sırasında gerçekleşeceğini yönetilmeyen işlev yürütür.  
  
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
 Aşağıdaki örnek, bir UNICODE dizesi yönetilmeyen bir işlev tarafından çağrılan yönetilen işlevdeki erişmek için gerekli verileri hazırlama gösterir. Yerel Unicode dizesini alırken yönetilen işlevi kullanarak yönetilen dizeye dönüştürür <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> yöntemi.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)