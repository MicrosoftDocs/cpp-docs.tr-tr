---
title: 'Nasıl yapılır: C++ birlikte çalışması kullanarak katıştırılmış işaretçileri sıralama | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- structures [C++], marshaling embedded pointers
- interop [C++], embedded pointers
- C++ Interop, embedded pointers
- marshaling [C++], embedded pointers
- pointers [C++], marshaling
- data marshaling [C++], embedded pointers
ms.assetid: 05fb8858-97f2-47aa-86b2-2c0ad713bdb2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3f0dab57fd9962975271d8105de64c729c6095fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129011"
---
# <a name="how-to-marshal-embedded-pointers-using-c-interop"></a>Nasıl yapılır: C++ Birlikte Çalışması Kullanarak Katıştırılmış İşaretçileri Sıralama
Aşağıdaki kod örnekleri kullan [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md) uygulamak için #pragma yönergeleri yönetilen ve yönetilmeyen işlevleri aynı dosyada, ancak bu işlevler ayrı dosyalarda tanımlanırsa aynı şekilde birlikte çalışır. Yalnızca yönetilmeyen işlevleri içeren dosyalar ile derlenmesi gerekmez [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, yönetilen bir işlevden işaretçileri içeren yapıyı alan yönetilmeyen işlev nasıl çağrılabilir gösterir. Yönetilen işlev yapısı örneği oluşturur ve new anahtar sözcüğüyle katıştırılmış işaretçi başlatır (yerine [yeni başvuru, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) anahtar sözcüğü). Bu yerel yığında bellek ayırdığından, atık toplama bastırmak için diziyi sabitlemek için gerek yoktur. Ancak, Bellek sızıntısını önlemek için bellek açıkça silinmelidir.  
  
```  
// marshal_embedded_pointer.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// unmanaged struct  
struct ListStruct {  
   int count;  
   double* item;  
};  
  
#pragma unmanaged  
  
void UnmanagedTakesListStruct(ListStruct list) {  
   printf_s("[unmanaged] count = %d\n", list.count);  
   for (int i=0; i<list.count; i++)  
      printf_s("array[%d] = %f\n", i, list.item[i]);  
}  
  
#pragma managed  
  
int main() {  
   ListStruct list;  
   list.count = 10;  
   list.item = new double[list.count];  
  
   Console::WriteLine("[managed] count = {0}", list.count);  
   Random^ r = gcnew Random(0);  
   for (int i=0; i<list.count; i++) {  
      list.item[i] = r->NextDouble() * 100.0;  
      Console::WriteLine("array[{0}] = {1}", i, list.item[i]);  
   }  
  
   UnmanagedTakesListStruct( list );  
   delete list.item;  
}  
```  
  
```Output  
[managed] count = 10  
array[0] = 72.624326996796  
array[1] = 81.7325359590969  
array[2] = 76.8022689394663  
array[3] = 55.8161191436537  
array[4] = 20.6033154021033  
array[5] = 55.8884794618415  
array[6] = 90.6027066011926  
array[7] = 44.2177873310716  
array[8] = 97.754975314138  
array[9] = 27.370445768987  
[unmanaged] count = 10  
array[0] = 72.624327  
array[1] = 81.732536  
array[2] = 76.802269  
array[3] = 55.816119  
array[4] = 20.603315  
array[5] = 55.888479  
array[6] = 90.602707  
array[7] = 44.217787  
array[8] = 97.754975  
array[9] = 27.370446  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)