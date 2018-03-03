---
title: "Nasıl yapılır: C++ birlikte çalışması kullanarak COM dizelerini sıralama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- COM [C++], marshaling strings
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 45a79f3aa78d229c71aba5a1d1144d05afe7bbd7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-com-strings-using-c-interop"></a>Nasıl yapılır: C++ Birlikte Çalışması Kullanarak COM Dizelerini Sıralama
Bu konuda nasıl BSTR (COM programlamada avantajlı temel dize biçimi) gösterilmektedir yönetilmeyen bir işleve ve tersi yönde yönetilen işlevden geçirildi. Diğer dizeler türleriyle birlikte çalışmak için aşağıdaki konulara bakın:  
  
-   [Nasıl yapılır: C++ Çalışabilirliği Kullanarak Unicode Dizelerini Sıralama](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [Nasıl yapılır: C++ Birlikte Çalışması Kullanarak ANSI Dizelerini Sıralama](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
 Aşağıdaki kod örnekleri kullan [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) uygulamak için #pragma yönergeleri yönetilen ve yönetilmeyen işlevleri aynı dosyada, ancak bu işlevler ayrı dosyalarda tanımlanırsa aynı şekilde birlikte çalışır. Yalnızca yönetilmeyen işlevleri içeren dosyalar ile derlenmesi gerekmez [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, nasıl BSTR (COM programlamasında kullanılan bir dize biçimi) geçtiğini gösterir yönetilen yönetilmeyen bir işleve gelen. Arama Yönetilen işlev <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> .NET System içeriğini BSTR gösterimini adresini elde edin. Bu işaretçinin kullanarak sabitlenir [pin_ptr (C + +/ CLI)](../windows/pin-ptr-cpp-cli.md) yönetilmeyen işlev çalışırken fiziksel adresini bir atık toplama döngüsü sırasında değiştirilmez emin olmak için. Çöp toplayıcı kadar belleği taşıması yasaklanmıştır [pin_ptr (C + +/ CLI)](../windows/pin-ptr-cpp-cli.md) kapsamının dışına gider.  
  
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
 Aşağıdaki örnek, nasıl BSTR geçtiğini gösterir yönetilmeyenden bir yönetilmeyen işlev. Yönetilen işlev dizesinde BSTR olarak kullanabilir veya kullanmak alma <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> öğesine dönüştürmek için bir <xref:System.String> işlevleri yönetilen diğer ile kullanım için. BSTR temsil eden bellek yönetilmeyen yığında ayrılmış olduğundan, hiçbir çöp toplama yönetilmeyen yığında olduğundan hiçbir sabitleme, gereklidir.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)