---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: PInvoke kullanarak katıştırılmış Işaretçileri sıralama'
title: 'Nasıl yapılır: PInvoke Kullanarak Katıştırılmış İşaretçileri Sıralama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- embedded pointers [C++]
- interop [C++], embedded pointers
- platform invoke [C++], embedded pointers
- marshaling [C++], embedded pointers
- data marshaling [C++], embedded pointers
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
ms.openlocfilehash: d31660a9a8ba345b380d442bb4484e332fe9d7cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302562"
---
# <a name="how-to-marshal-embedded-pointers-using-pinvoke"></a>Nasıl yapılır: PInvoke Kullanarak Katıştırılmış İşaretçileri Sıralama

Yönetilmeyen DLL 'lerde uygulanan işlevler, platform Invoke (P/Invoke) işlevi kullanılarak yönetilen koddan çağrılabilir. DLL için kaynak kodu kullanılamıyorsa, her çalışma için P/Invoke tek seçenektir. Ancak, diğer .NET dillerinin aksine, Visual C++ P/Invoke için bir alternatif sağlar. Daha fazla bilgi için bkz. [C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) ve [nasıl yapılır: C++ birlikte çalışması kullanarak katıştırılmış işaretçileri sıralama](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).

## <a name="example"></a>Örnek

Yapıları yerel koda geçirmek için, yerel yapıya veri düzeni bakımından eşdeğer bir yönetilen yapının oluşturulması gerekir. Ancak, işaretçiler içeren yapılar için özel işleme gerekir. Yerel yapıdaki her katıştırılmış işaretçi için, yapının yönetilen sürümü türünün bir örneğini içermelidir <xref:System.IntPtr> . Ayrıca, bu örneklerin belleği,, ve yöntemleri kullanılarak açıkça ayrılmalıdır, başlatılmalıdır ve serbest <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A> bırakılır <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A> <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> .

Aşağıdaki kod, yönetilmeyen ve yönetilen bir modülden oluşur. Yönetilmeyen modül, bir işaretçi içeren ListString adlı bir yapıyı ve TakesListStruct adlı bir işlevi kabul eden bir işlevi tanımlayan bir DLL 'dir. Yönetilen modül, TakesListStruct işlevini içeri aktaran ve Double * değerinin bir örnekle temsil edildiği hariç, yerel ListStruct öğesine denk gelen MListStruct adlı bir yapıyı tanımlayan bir komut satırı uygulamasıdır <xref:System.IntPtr> . TakesListStruct çağrılmadan önce Main işlevi, bu alanın başvurduğu belleği ayırır ve başlatır.

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

Geleneksel #include yönergesini kullanarak, DLL 'nin hiçbir kısmının yönetilen koda sunulmadığını unutmayın. Aslında, DLL 'ye yalnızca çalışma zamanında erişilir. bu nedenle, ile içeri aktarılan işlevlerle ilgili sorunlar <xref:System.Runtime.InteropServices.DllImportAttribute> derleme zamanında algılanmaz.

## <a name="see-also"></a>Ayrıca bkz.

[C++ ' ta açık PInvoke kullanma (DllImport özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
