---
title: 'Nasıl yapılır: PInvoke kullanarak dizileri sıralama | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- marshaling [C++], arrays
- platform invoke [C++], arrays
- interop [C++], arrays
- data marshaling [C++], arrays
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9c07aba54f621011d2dd4831d7dfb6b536073fa9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395693"
---
# <a name="how-to-marshal-arrays-using-pinvoke"></a>Nasıl yapılır: PInvoke Kullanarak Dizileri Sıralama

Bu konuda, C stili dizeler, CLR dize türü kullanılarak çağrılabilir kabul nasıl yerel işlevleri açıklanmaktadır. <xref:System.String> desteği .NET Framework Platform çağırma kullanma. Visual C++ programcıları (uygun olduğunda) C++ birlikte çalışabilirlik özellikleri kullanmaları önerilir, çünkü çok az derleme zamanı hata raporlama, tür açısından güvenli değildir ve uygulamak can sıkıcı olabilir, P/Invoke sağlar. Yönetilmeyen API'ın bir DLL olarak paketlenmesi ve kaynak kodu yok, P/Invoke tek seçenektir (Aksi takdirde bkz [C++ Çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)).

## <a name="example"></a>Örnek

Yerel ve yönetilen diziler bellekte farklı şekilde düzenlenmiştir olduğundan, bunları yönetilen veya yönetilmeyen sınırında başarıyla geçirme dönüştürme veya hazırlama gerektirir. Bu konu, yönetilen koddan nasıl basit (taşınabilir) öğelerin bir dizisi yerel işlevlere geçirilebilir gösterir.

Genel olarak, yönetilen ve yönetilmeyen verileri hazırlama true olduğunda <xref:System.Runtime.InteropServices.DllImportAttribute> özniteliği, bir yönetilen giriş noktası için kullanılacak her bir yerel işlev oluşturmak için kullanılır. Dizileri bağımsız değişkenler almayan işlevleri söz konusu olduğunda <xref:System.Runtime.InteropServices.MarshalAsAttribute> özniteliği yanı derleyici için verileri nasıl sıralanacağını belirlemek için kullanılmalıdır. Aşağıdaki örnekte, <xref:System.Runtime.InteropServices.UnmanagedType> numaralandırması yönetilen dizi bir C tarzı dizi olarak sıralanmış olduğunu belirtmek için kullanılır.

Aşağıdaki kod, yönetilmeyen ve yönetilen bir modül oluşur. Yönetilmeyen tamsayı dizisi kabul eden bir işlev tanımlayan bir DLL modülüdür. Bu işlev alır ancak açısından yönetilen bir diziyi tanımlar ve kullanan yönetilen bir komut satırı uygulaması olduğundan ikinci Modülü <xref:System.Runtime.InteropServices.MarshalAsAttribute> dizi çağrıldığında bir yerel dizi dönüştürülmesi gerektiğini belirtmek için özniteliği.

Yönetilen modül/CLR ile derlenir.

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

Geleneksel aracılığıyla yönetilen koda hiçbir kısmı DLL kullanıma sunulduğunu unutmayın #include yönergesi. DLL yalnızca çalışma zamanında erişilir, aslında, İşlevler ile ilgili sorunlar ile içeri aktarılan <xref:System.Runtime.InteropServices.DllImportAttribute> derleme zamanında algılanmaz.

## <a name="see-also"></a>Ayrıca Bkz.

[C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)