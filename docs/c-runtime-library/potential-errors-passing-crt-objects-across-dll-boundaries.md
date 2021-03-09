---
title: CRT Nesnelerini DLL Sınırlarından Geçirirken Olası Hatalar
description: Microsoft C çalışma zamanı nesnelerini dinamik bağlantı kitaplığı (DLL) sınırında geçirirken ortaya çıkabilecek olası sorunlara genel bakış.
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- DLL conflicts [C++]
ms.assetid: c217ffd2-5d9a-4678-a1df-62a637a96460
ms.openlocfilehash: 7af0fe8b5819bf428753c9ec71099113df0fa79e
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514557"
---
# <a name="potential-errors-passing-crt-objects-across-dll-boundaries"></a>CRT Nesnelerini DLL Sınırlarından Geçirirken Olası Hatalar

Dll sınırında işlev çağrıları aracılığıyla bir DLL içine veya dışına Dosya tutamaçları, yerel ayarlar ve ortam değişkenleri gibi C çalışma zamanı (CRT) nesneleri geçirdiğinizde, dll veya DLL 'e çağrı yapan herhangi bir dosya varsa, CRT kitaplıklarının farklı kopyalarını kullanabilirsiniz.

Bellek (ya da ya da dolaylı olarak, vb.) tahsis ettiğinizde ilgili bir sorun oluşabilir `new` `malloc` `strdup` `strstreambuf::str` ve sonra bir IŞARETÇIYI serbest bırakıldığında bir dll sınırı boyunca geçirin. Bu, DLL ve tüketicileri CRT kitaplıklarının farklı kopyalarını kullanıyorsa, bir bellek erişim ihlaline veya yığın bozulmasına neden olabilir.

Bu sorunun başka bir belirtisi, hata ayıklama sırasında çıkış sırasında çıktı penceresinde hata `HEAP[]: Invalid Address specified to RtlValidateHeap(#,#)`

## <a name="causes"></a>Nedenler

CRT kitaplığı 'nın her bir kopyasının, uygulamanız veya DLL 'niz tarafından iş parçacığı yerel depolama alanında tutulan ayrı ve farklı bir durumu vardır.

Dosya tutamaçları, ortam değişkenleri ve yerel ayarlar gibi CRT nesneleri yalnızca, bu nesnelerin ayrıldığı veya ayarlandığı uygulamadaki veya DLL 'deki CRT kopyası için geçerlidir. Bir DLL ve istemcileri, CRT kitaplığı 'nın farklı kopyalarını kullandıklarında, bu CRT nesneleri DLL sınırında geçiremezsiniz ve diğer tarafta doğru bir şekilde kullanılmasını bekleyebilir. Bu, Visual Studio 2015 ve üzeri sürümlerde Evrensel CRT 'tan önceki CRT sürümlerden oluşur.

Visual Studio 2013 veya daha önceki sürümleriyle oluşturulmuş her Visual Studio sürümü için sürüme özgü bir CRT kitaplığı vardı. Veri yapıları ve adlandırma kuralları gibi CRT 'ın iç uygulama ayrıntıları her sürümde farklıydı. CRT 'nin bir sürümü için derlenen kodu, CRT DLL 'nin farklı bir sürümüne dinamik olarak bağlama hiçbir şekilde desteklenmez. Bazen, tasarım yerine bir şanslar nedeniyle çalışacaktır.

CRT kitaplığı 'nın her kopyasının kendi yığın Yöneticisi olduğundan, bir CRT kitaplığında bellek ayırarak ve bir CRT kitaplığının farklı bir kopyası tarafından boşaltılacak şekilde işaretçiyi bir DLL sınırı üzerinde geçirerek yığın bozulmasına neden olabilir. Dll 'nizi, dll sınırında CRT nesneleri geçireceğini veya bellek ayırır ve DLL 'nin dışında serbest olmasını bekliyorsa, DLL 'nin istemcilerinin, DLL ile aynı CRT kitaplığı kopyasını kullanması gerekir.

DLL ve istemcileri normalde, her ikisi de aynı CRT DLL sürümüne bağlandığında CRT kitaplığı 'nın aynı kopyasını kullanır. Visual Studio 2015 ve üzeri Windows 10 ' da bulunan Universal CRT kitaplığı 'nın DLL sürümü artık merkezi olarak dağıtılan bir Windows bileşenidir (ucrtbase.dll), bu, Visual Studio 2015 ve sonraki sürümlerle oluşturulmuş uygulamalar için aynıdır. Ancak, CRT kodu özdeş olsa bile, farklı bir yığın kullanan bir bileşene tek bir yığında ayrılan bellek veremezsiniz.

## <a name="example-pass-file-handle-across-dll-boundary"></a>Örnek: dosya işleyicisini DLL sınırı arasında geçir

### <a name="description"></a>Description

Bu örnek, bir DLL sınırının tamamında bir dosya işleyicisini geçirir.

DLL ve. exe dosyaları ile oluşturulmuştur `/MD` , bu sayede CRT 'nin tek bir kopyasını paylaşırlar.

`/MT`CRT 'nin ayrı kopyalarını kullanmaları için ile yeniden derleme yaparsanız, sonuç **test1Main.exe** çalıştırmak bir erişim ihlaline neden olur.

```cpp
// test1Dll.cpp
// compile with: cl /EHsc /W4 /MD /LD test1Dll.cpp
#include <stdio.h>
__declspec(dllexport) void writeFile(FILE *stream)
{
   char   s[] = "this is a string\n";
   fprintf( stream, "%s", s );
   fclose( stream );
}
```

```cpp
// test1Main.cpp
// compile with: cl /EHsc /W4 /MD test1Main.cpp test1Dll.lib
#include <stdio.h>
#include <process.h>
void writeFile(FILE *stream);

int main(void)
{
   FILE  * stream;
   errno_t err = fopen_s( &stream, "fprintf.out", "w" );
   writeFile(stream);
   system( "type fprintf.out" );
}
```

```Output
this is a string
```

## <a name="example-pass-environment-variables-across-dll-boundary"></a>Örnek: ortam değişkenlerini DLL sınırının tamamında geçir

### <a name="description"></a>Description

Bu örnek, bir DLL sınırının tamamında ortam değişkenlerini geçirir.

```cpp
// test2Dll.cpp
// compile with: cl /EHsc /W4 /MT /LD test2Dll.cpp
#include <stdio.h>
#include <stdlib.h>

__declspec(dllexport) void readEnv()
{
   char *libvar;
   size_t libvarsize;

   /* Get the value of the MYLIB environment variable. */
   _dupenv_s( &libvar, &libvarsize, "MYLIB" );

   if( libvar != NULL )
      printf( "New MYLIB variable is: %s\n", libvar);
   else
      printf( "MYLIB has not been set.\n");
   free( libvar );
}
```

```cpp
// test2Main.cpp
// compile with: cl /EHsc /W4 /MT test2Main.cpp test2dll.lib
#include <stdlib.h>
#include <stdio.h>

void readEnv();

int main( void )
{
   _putenv( "MYLIB=c:\\mylib;c:\\yourlib" );
   readEnv();
}
```

```Output
MYLIB has not been set.
```

Hem DLL hem de. exe dosyası, `/MD` CRT 'nın yalnızca bir kopyasının kullanıldığı şekilde derlense, program başarıyla çalışır ve aşağıdaki çıktıyı üretir:

```
New MYLIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>Ayrıca bkz.

[C çalışma zamanı (CRT) ve C++ standart kitaplığı (STL) `.lib` dosyaları](../c-runtime-library/crt-library-features.md)
