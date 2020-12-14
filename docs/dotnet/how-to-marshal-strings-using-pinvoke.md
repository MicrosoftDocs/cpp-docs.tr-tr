---
description: 'Daha fazla bilgi edinin: nasıl yapılır: PInvoke kullanarak dizeleri sıralama'
title: 'Nasıl yapılır: PInvoke Kullanarak Dizeleri Sıralama'
ms.custom: get-started-article
ms.date: 09/09/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- data marshaling [C++], strings
- platform invoke [C++], strings
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
ms.openlocfilehash: 29bec9a05d0425d1ce2cde42b89dacc7818ebac1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302575"
---
# <a name="how-to-marshal-strings-using-pinvoke"></a>Nasıl yapılır: PInvoke Kullanarak Dizeleri Sıralama

Bu konu, .NET Framework platform çağırma desteği kullanılarak System:: String CLR dize türü kullanılarak C stili dizeleri kabul eden yerel işlevlerin nasıl çağrılacağını açıklar. Visual C++ programcıların C++ birlikte çalışma özelliklerini kullanması önerilir, çünkü P/Invoke çok az sayıda derleme zamanı hatası raporlama sağladığından, tür kullanımı güvenli değildir ve uygulanması sıkıcı olabilir. Yönetilmeyen API bir DLL olarak paketleniyorsa ve kaynak kodu kullanılabilir değilse, P/Invoke tek seçenektir, ancak Aksi halde [C++ birlikte çalışabilirliği (örtük PInvoke) kullanma](../dotnet/using-cpp-interop-implicit-pinvoke.md)konusuna bakın.

Yönetilen ve yönetilmeyen dizeler bellekte farklı şekilde düzenlenir, böylece yönetilen dizelerin yönetilmeyen işlevlere geçirilmesi, <xref:System.Runtime.InteropServices.MarshalAsAttribute> derleyicinin dize verilerini doğru ve güvenli bir şekilde sıralama için gereken dönüştürme mekanizmalarını eklemesini ister.

Yalnızca iç veri türleri kullanan işlevlerde olduğu gibi, <xref:System.Runtime.InteropServices.DllImportAttribute> yönetilen giriş noktalarını yerel işlevlere bildirmek için kullanılır, ancak--dizeleri iletmek için, bu giriş noktalarını C stili dizeler olarak tanımlamak yerine, türü için bir tanıtıcı <xref:System.String> kullanılabilir. Bu, derleyicinin gerekli dönüştürmeyi gerçekleştiren kodu eklemesini ister. Bir dize alan yönetilmeyen bir işlevde her bir işlev bağımsız değişkeni için, <xref:System.Runtime.InteropServices.MarshalAsAttribute> dize nesnesinin yerel Işleve C stili dize olarak sıralanması gerektiğini göstermek için özniteliği kullanılmalıdır.

Sıralayıcı, yönetilmeyen işleve, yönetilen dizeyi sabitledi ve yönetilmeyen bir dizeye geçirilen yerel olarak ayrılmış bir dizeye kopyalayan bir gizli sarmalayıcı yordamının çağrısını sarmalanmış olarak sarmalar. Yönetilmeyen işlev döndürüldüğünde, sarmalayıcı kaynağı siler veya yığından ise sarmalayıcı kapsam dışına geçtiğinde geri kazanılır. Yönetilmeyen işlev bu bellekten sorumlu değildir. Yönetilmeyen kod yalnızca kendi CRT tarafından ayarlanan yığındaki belleği oluşturur ve siler, bu nedenle hazırlayıcısı ile farklı bir CRT sürümü kullanılarak hiçbir sorun yoktur.

Yönetilmeyen işleviniz, dönüş değeri veya out parametresi olarak bir dize döndürürse, Sıralayıcı onu yeni bir yönetilen dizeye kopyalar ve ardından belleği serbest bırakır. Daha fazla bilgi için bkz. [varsayılan sıralama davranışı](/dotnet/framework/interop/default-marshaling-behavior) ve [Platform çağırma ile verileri sıralama](/dotnet/framework/interop/marshaling-data-with-platform-invoke).

## <a name="example"></a>Örnek

Aşağıdaki kod, yönetilmeyen ve yönetilen bir modülden oluşur. Yönetilmeyen modül, bir char * biçiminde C stili bir ANSI dizeyi kabul eden TakesAString adlı bir işlevi tanımlayan bir DLL 'dir. Yönetilen modül, TakesAString işlevini içeri aktaran, ancak bunu bir char yerine yönetilen System. String olarak tanımlayan bir komut satırı uygulamasıdır \* . <xref:System.Runtime.InteropServices.MarshalAsAttribute>Özniteliği, TakesAString çağrıldığında yönetilen dizenin nasıl sıralanması gerektiğini belirtmek için kullanılır.

```cpp
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

```cpp
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

Bu teknik, dizenin bir kopyasının yönetilmeyen yığında oluşturulmasına neden olur, bu nedenle dizedeki yerel işlev tarafından yapılan değişiklikler, dizenin yönetilen kopyasına yansıtılmayacaktır.

Geleneksel #include yönergesi aracılığıyla, DLL 'nin hiçbir kısmının yönetilen koda sunulmadığını unutmayın. Aslında, DLL 'ye yalnızca çalışma zamanında erişilir. bu nedenle, ile içeri aktarılan işlevlerle ilgili sorunlar `DllImport` derleme zamanında algılanmaz.

## <a name="see-also"></a>Ayrıca bkz.

[C++ ' ta açık PInvoke kullanma (DllImport özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
