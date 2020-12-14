---
description: 'Daha fazla bilgi edinin: nasıl yapılır: PInvoke kullanarak dizileri sıralama'
title: 'Nasıl yapılır: PInvoke Kullanarak Dizileri Sıralama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling [C++], arrays
- platform invoke [C++], arrays
- interop [C++], arrays
- data marshaling [C++], arrays
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
ms.openlocfilehash: 90fd7b2cbefe2fb3621f512d49fbc088240922a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258232"
---
# <a name="how-to-marshal-arrays-using-pinvoke"></a>Nasıl yapılır: PInvoke Kullanarak Dizileri Sıralama

Bu konu, <xref:System.String> .NET Framework platform çağırma desteği KULLANıLARAK CLR dize türü kullanılarak C stili dizelerin kabul edileceği yerel işlevlerin nasıl çağrılacağını açıklar. Visual C++ programcıların C++ birlikte çalışma özelliklerini kullanması önerilir, çünkü P/Invoke çok az sayıda derleme zamanı hatası raporlama sağladığından, tür kullanımı güvenli değildir ve uygulanması sıkıcı olabilir. Yönetilmeyen API bir DLL olarak paketlenmişse ve kaynak kodu kullanılabilir değilse, P/Invoke tek seçenektir (Aksi takdirde, bkz. [C++ birlikte çalışabilirliği (örtük PInvoke) kullanma](../dotnet/using-cpp-interop-implicit-pinvoke.md)).

## <a name="example"></a>Örnek

Yerel ve yönetilen diziler bellekte farklı şekilde düzenlendiği için, yönetilen/yönetilmeyen sınır genelinde başarıyla geçirilmesi dönüştürme veya sıralama gerektirir. Bu konu başlığı altında, yönetilen koddan yerel işlevlere bir dizi basit (blitable) öğe geçirilebileceğini gösterir.

Genel olarak yönetilen/yönetilmeyen veri hazırlamayı doğru olduğu <xref:System.Runtime.InteropServices.DllImportAttribute> için, özniteliği kullanılacak her yerel işlev için bir yönetilen giriş noktası oluşturmak üzere kullanılır. Dizileri bağımsız değişken olarak alan işlevler söz konusu olduğunda, <xref:System.Runtime.InteropServices.MarshalAsAttribute> öznitelik kullanılmalıdır ve derleyicinin verilerin nasıl sıralandığına yönelik olarak belirtilmesi gerekir. Aşağıdaki örnekte, <xref:System.Runtime.InteropServices.UnmanagedType> sıralama yönetilen dizinin C stili dizi olarak sıralandığını göstermek için kullanılır.

Aşağıdaki kod, yönetilmeyen ve yönetilen bir modülden oluşur. Yönetilmeyen modül, tamsayılar dizisini kabul eden bir işlevi tanımlayan bir DLL 'dir. İkinci modül, bu işlevi içeri aktaran, ancak yönetilen bir dizi açısından tanımlayan bir yönetilen komut satırı uygulamasıdır ve <xref:System.Runtime.InteropServices.MarshalAsAttribute> dizinin çağrıldığında Yerel bir diziye dönüştürülmesi gerektiğini belirtmek için özniteliğini kullanır.

Yönetilen modül/clrile derlenir.

```cpp
// TraditionalDll4.cpp
// compile with: /LD /EHsc
#include <iostream>

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   TRADITIONALDLL_API void TakesAnArray(int len, int[]);
}

void TakesAnArray(int len, int a[]) {
   printf_s("[unmanaged]\n");
   for (int i=0; i<len; i++)
      printf("%d = %d\n", i, a[i]);
}
```

```cpp
// MarshalBlitArray.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value struct TraditionalDLL {
   [DllImport("TraditionalDLL4.dll")]
   static public void TakesAnArray(
   int len,[MarshalAs(UnmanagedType::LPArray)]array<int>^);
};

int main() {
   array<int>^ b = gcnew array<int>(3);
   b[0] = 11;
   b[1] = 33;
   b[2] = 55;
   TraditionalDLL::TakesAnArray(3, b);

   Console::WriteLine("[managed]");
   for (int i=0; i<3; i++)
      Console::WriteLine("{0} = {1}", i, b[i]);
}
```

Geleneksel #include yönergesi aracılığıyla, DLL 'nin hiçbir kısmının yönetilen koda sunulmadığını unutmayın. Aslında, DLL çalışma zamanında erişildiği için, ile içeri aktarılan işlevlerle ilgili sorunlar <xref:System.Runtime.InteropServices.DllImportAttribute> derleme zamanında algılanmaz.

## <a name="see-also"></a>Ayrıca bkz.

[C++ ' ta açık PInvoke kullanma (DllImport özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
