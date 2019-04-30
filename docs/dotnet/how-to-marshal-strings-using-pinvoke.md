---
title: 'Nasıl yapılır: PInvoke kullanarak dizeleri sıralama hazırlama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- data marshaling [C++], strings
- platform invoke [C++], strings
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
ms.openlocfilehash: f316e33f1711ea0053fb68c0af7e89f90b793e05
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404409"
---
# <a name="how-to-marshal-strings-using-pinvoke"></a>Nasıl yapılır: PInvoke kullanarak dizeleri sıralama hazırlama

Bu konuda, C stili dizeler, CLR dizesi kullanılarak çağrılabilir kabul nasıl yerel işlevleri açıklanmaktadır. .NET Framework Platform çağırma desteğini kullanarak System::String yazın. Visual C++ programcıları (uygun olduğunda) C++ birlikte çalışabilirlik özellikleri kullanmaları önerilir, çünkü çok az derleme zamanı hata raporlama, tür açısından güvenli değildir ve uygulamak can sıkıcı olabilir, P/Invoke sağlar. Yönetilmeyen API'ın bir DLL olarak paketlenmesi ve kaynak kodu yok, P/Invoke tek seçenektir, ancak Aksi takdirde bkz [C++ Çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

Yönetilen ve yönetilmeyen dizeleri farklı düzenlenir bellekte, bu nedenle dizelerden yönetilmeyen işlevlerle yönetilen gerektirir <xref:System.Runtime.InteropServices.MarshalAsAttribute> string veri hazırlama için gerekli dönüştürme mekanizmaları eklemek için derleyicisinin özniteliği düzgün ve güvenli bir şekilde.

Yalnızca iç veri türlerini kullanan işlevler gibi ile <xref:System.Runtime.InteropServices.DllImportAttribute> yönetilen giriş noktaları C stili dizeler, işleyici olarak alıp bu giriş noktaları tanımlamak yerine dizgiler için yerel işlevler halinde, ancak--bildirmek için kullanılan <xref:System.String> türü Bunun yerine kullanılabilir. Bu, derleyicinin gerekli dönüştürme uygulayan kod eklemesini ister. Her işlev bağımsız değişkeni bir dize alır, yönetilmeyen bir işlevde <xref:System.Runtime.InteropServices.MarshalAsAttribute> öznitelik dize nesnesine yerel işlev C stili dize olarak sıralanması gerektiğini belirtmek için kullanılması gerekir.

## <a name="example"></a>Örnek

Aşağıdaki kod, bir yönetilmeyen ve yönetilen bir modül oluşur. Yönetilmeyen bir ANSI C stili dize şeklinde char * kabul eden TakesAString adında bir işlevi tanımlayan bir DLL modülüdür. Yönetilen modül TakesAString işlevini alır, ancak bir karakter yerine yönetilen System.String olarak tanımlayan bir komut satırı uygulamasıdır\*. <xref:System.Runtime.InteropServices.MarshalAsAttribute> Özniteliğini, yönetilen dize TakesAString çağrıldığında nasıl sıralanması gerektiğini belirtmek için kullanılır.

```
// TraditionalDll2.cpp
// compile with: /LD /EHsc
#include <windows.h>
#include <stdio.h>
#include <iostream>

using namespace std;

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   TRADITIONALDLL_API void TakesAString(char*);
}

void TakesAString(char* p) {
   printf_s("[unmanaged] %s\n", p);
}
```

```
// MarshalString.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value struct TraditionalDLL
{
   [DllImport("TraditionalDLL2.dll")]
      static public void
      TakesAString([MarshalAs(UnmanagedType::LPStr)]String^);
};

int main() {
   String^ s = gcnew String("sample string");
    Console::WriteLine("[managed] passing managed string to unmanaged function...");
   TraditionalDLL::TakesAString(s);
   Console::WriteLine("[managed] {0}", s);
}
```

Bu teknik, yönetilmeyen yığındaki dizenin yönetilen kopyalama dizeye yerel işlev tarafından yapılan değişiklikler yansıtılmaz şekilde oluşturulması için dizenin bir kopyasını neden olur.

Geleneksel aracılığıyla yönetilen koda hiçbir kısmı DLL kullanıma sunulduğunu unutmayın #include yönergesi. Aslında, ile içeri aktarılan işlevlere sahip sorunlar için DLL yalnızca çalışma zamanında erişilir `DllImport` derleme zamanında algılanmaz.

## <a name="see-also"></a>Ayrıca bkz.

[C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
