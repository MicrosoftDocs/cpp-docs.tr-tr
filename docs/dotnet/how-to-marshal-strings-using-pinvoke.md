---
title: 'Nasıl yapılır: PInvoke kullanarak dizeleri sıralama'
ms.custom: get-started-article
ms.date: 09/09/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- data marshaling [C++], strings
- platform invoke [C++], strings
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
ms.openlocfilehash: d3b39a4ce40de2a26ffba4f52ab1e39c94767089
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907560"
---
# <a name="how-to-marshal-strings-using-pinvoke"></a>Nasıl yapılır: PInvoke kullanarak dizeleri sıralama

Bu konu, .NET Framework platform çağırma desteği kullanılarak System:: String CLR dize türü kullanılarak C stili dizeleri kabul eden yerel işlevlerin nasıl çağrılacağını açıklar. Visual C++ programcýlarının (mümkün olduğunda) C++ , P/Invoke çok az derleme zamanı hata raporlama sağladığından, tür kullanımı güvenli olmadığından ve uygulanması sıkıcı olabileceğinden, birlikte çalışma özelliklerinin kullanılması önerilir. Yönetilmeyen API bir DLL olarak paketleniyorsa ve kaynak kodu kullanılabilir değilse, P/Invoke tek seçenektir, ancak başka bir şekilde [birlikte çalışabilirlik (örtük PInvoke) kullanma C++ ](../dotnet/using-cpp-interop-implicit-pinvoke.md)konusuna bakın.

Yönetilen ve yönetilmeyen dizeler bellekte farklı şekilde düzenlenir, böylece yönetilen dizelerin yönetilmeyen işlevlere <xref:System.Runtime.InteropServices.MarshalAsAttribute> geçirilmesi, derleyicinin dize verilerini hazırlama için gereken dönüştürme mekanizmalarını eklemesini ister doğru ve güvenli.

Yalnızca iç veri türleri kullanan işlevlerde olduğu gibi, <xref:System.Runtime.InteropServices.DllImportAttribute> yerel işlevlere yönetilen giriş noktalarını bildirmek için kullanılır, ancak--dizeleri iletmek için, bu giriş noktalarını C stili dizeler yerine tanımlamak yerine, <xref:System.String> türü için bir tanıtıcı Bunun yerine kullanılabilir. Bu, derleyicinin gerekli dönüştürmeyi gerçekleştiren kodu eklemesini ister. Bir dize alan yönetilmeyen bir işlevde her bir işlev bağımsız değişkeni için, <xref:System.Runtime.InteropServices.MarshalAsAttribute> dize nesnesinin yerel işleve C stili dize olarak sıralanması gerektiğini göstermek için özniteliği kullanılmalıdır.

Sıralayıcı, yönetilmeyen işleve, yönetilen dizeyi sabitledi ve yönetilmeyen bir dizeye geçirilen yerel olarak ayrılmış bir dizeye kopyalayan bir gizli sarmalayıcı yordamının çağrısını sarmalanmış olarak sarmalar. Yönetilmeyen işlev döndürüldüğünde, sarmalayıcı kaynağı siler veya yığından ise sarmalayıcı kapsam dışına geçtiğinde geri kazanılır. Yönetilmeyen işlev bu bellekten sorumlu değildir. Yönetilmeyen kod yalnızca kendi CRT tarafından ayarlanan yığındaki belleği oluşturur ve siler, bu nedenle hazırlayıcısı ile farklı bir CRT sürümü kullanılarak hiçbir sorun yoktur.

Yönetilmeyen işleviniz, dönüş değeri veya out parametresi olarak bir dize döndürürse, Sıralayıcı onu yeni bir yönetilen dizeye kopyalar ve ardından belleği serbest bırakır. Daha fazla bilgi için bkz. [varsayılan sıralama davranışı](/dotnet/framework/interop/default-marshaling-behavior) ve [Platform çağırma ile verileri sıralama](/dotnet/framework/interop/marshaling-data-with-platform-invoke).

## <a name="example"></a>Örnek

Aşağıdaki kod, yönetilmeyen ve yönetilen bir modülden oluşur. Yönetilmeyen modül, bir char * biçiminde C stili bir ANSI dizeyi kabul eden TakesAString adlı bir işlevi tanımlayan bir DLL 'dir. Yönetilen modül, TakesAString işlevini içeri aktaran, ancak bunu bir Char\*yerine yönetilen System. String olarak tanımlayan bir komut satırı uygulamasıdır. <xref:System.Runtime.InteropServices.MarshalAsAttribute> Özniteliği, TakesAString çağrıldığında yönetilen dizenin nasıl sıralanması gerektiğini belirtmek için kullanılır.

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

Bu teknik, dizenin bir kopyasının yönetilmeyen yığında oluşturulmasına neden olur, bu nedenle dizedeki yerel işlev tarafından yapılan değişiklikler, dizenin yönetilen kopyasına yansıtılmayacaktır.

Geleneksel #include yönergesi aracılığıyla, DLL 'nin hiçbir kısmının yönetilen koda sunulmadığını unutmayın. Aslında, dll 'ye yalnızca çalışma zamanında erişilir. bu nedenle, ile `DllImport` içeri aktarılan işlevlerle ilgili sorunlar derleme zamanında algılanmaz.

## <a name="see-also"></a>Ayrıca bkz.

[C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
