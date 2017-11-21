---
title: "Nasıl yapılır: PInvoke kullanarak katıştırılmış işaretçileri sıralama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- embedded pointers [C++]
- interop [C++], embedded pointers
- platform invoke [C++], embedded pointers
- marshaling [C++], embedded pointers
- data marshaling [C++], embedded pointers
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c8f6716a11919c300dc3153ca678767503a35088
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-marshal-embedded-pointers-using-pinvoke"></a>Nasıl yapılır: PInvoke Kullanarak Katıştırılmış İşaretçileri Sıralama
Platform Çağırma (P/Invoke) işlevselliği kullanılarak yönetilen koddan yönetilmeyen DLL'lere uygulanan işlevler çağrılabilir. DLL için kaynak kodunu kullanılabilir durumda değilse, P/Invoke birlikte için tek seçenektir. Ancak, diğer .NET dilleri, Visual C++ alternatif P/Invoke sağlar. Daha fazla bilgi için bkz: [C++ Çalışabilirliği kullanarak (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) ve [nasıl yapılır: sıralama katıştırılmış işaretçileri C++ Çalışabilirliği kullanarak](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).  
  
## <a name="example"></a>Örnek  
 Yerel kod yapıları geçirme yerel yapısı için veri düzeni bakımından eşdeğer bir gruba bir yönetilen yapının oluşturduğunuz gerektirir. Ancak, işaretçiler içeren yapılar özel işleme gerektirir. Yerel yapısındaki her katıştırılmış işaretçi için yönetilen sürümün yapısı örneği içermelidir <xref:System.IntPtr> türü. Ayrıca, bellek açıkça bu örnekler tahsis edilen için başlatıldı ve kullanılarak serbest <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A>, <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A>, ve <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> yöntemleri.  
  
 Aşağıdaki kod, bir yönetilmeyen ve yönetilen bir modül oluşur. Yönetilmeyen modül bir işaretçi içeriyor ListString olarak adlandırılan bir yapıyı kabul eden bir işlev ve TakesListStruct adlı bir işlev tanımlayan bir DLL'dir. Yönetilen modül TakesListStruct işlevini alır ve çift * ile temsil edilen ancak bu, yerel ListStruct ile eşdeğer olan MListStruct olarak adlandırılan bir yapıyı tanımlayan bir komut satırı uygulamasıdır bir <xref:System.IntPtr> örneği. TakesListStruct öğesini çağırmadan önce main işlevi ayırır ve bu alana başvuran bellek başlatır.  
  
 / CLR, ancak/CLR ile yönetilen modül derlenmiş: pure de çalışır. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
```cpp  
// TraditionalDll6.cpp  
// compile with: /EHsc /LD  
#include <stdio.h>  
#include <iostream>  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
#pragma pack(push, 8)  
struct ListStruct {  
   int count;  
   double* item;  
};  
#pragma pack(pop)  
  
extern "C" {  
   TRADITIONALDLL_API void TakesListStruct(ListStruct);  
}  
  
void TakesListStruct(ListStruct list) {  
   printf_s("[unmanaged] count = %d\n", list.count);  
   for (int i=0; i<list.count; i++)  
      printf_s("array[%d] = %f\n", i, list.item[i]);  
}  
```  
  
```cpp  
// EmbeddedPointerMarshalling.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Sequential, Pack=8)]  
value struct MListStruct {  
   int count;  
   IntPtr item;  
};  
  
value struct TraditionalDLL {  
    [DllImport("TraditionalDLL6.dll")]  
   static public void TakesListStruct(MListStruct);  
};  
  
int main() {  
   array<double>^ parray = gcnew array<double>(10);  
   Console::WriteLine("[managed] count = {0}", parray->Length);  
  
   Random^ r = gcnew Random();  
   for (int i=0; i<parray->Length; i++) {  
      parray[i] = r->NextDouble() * 100.0;  
      Console::WriteLine("array[{0}] = {1}", i, parray[i]);  
   }  
  
   int size = Marshal::SizeOf(double::typeid);  
   MListStruct list;  
   list.count = parray->Length;  
   list.item = Marshal::AllocCoTaskMem(size * parray->Length);  
  
   for (int i=0; i<parray->Length; i++) {  
      IntPtr t = IntPtr(list.item.ToInt32() + i * size);  
      Marshal::StructureToPtr(parray[i], t, false);  
   }  
  
   TraditionalDLL::TakesListStruct( list );  
   Marshal::FreeCoTaskMem(list.item);  
}  
```  
  
 DLL hiçbir bölümünün geleneksel kullanarak yönetilen kod açıktır Not #include yönergesi. İle içeri aktarılan işlevlerle sorunlar aslında, DLL yalnızca çalışma zamanında erişilir, böylece <xref:System.Runtime.InteropServices.DllImportAttribute> derleme zamanında algılanmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ (DllImport özniteliği) açık PInvoke kullanma](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)