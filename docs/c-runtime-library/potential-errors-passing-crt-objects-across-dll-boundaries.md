---
title: CRT Nesnelerini DLL Sınırlarından Geçirirken Olası Hatalar
ms.date: 11/04/2016
helpviewer_keywords:
- DLL conflicts [C++]
ms.assetid: c217ffd2-5d9a-4678-a1df-62a637a96460
ms.openlocfilehash: 31f9d9aceba167b516c9d37724e240f1bc4586e1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62342529"
---
# <a name="potential-errors-passing-crt-objects-across-dll-boundaries"></a>CRT Nesnelerini DLL Sınırlarından Geçirirken Olası Hatalar

C geçirdiğinizde çalışma zamanı (CRT) dosya tanıtıcıları, yerel ve ortam değişkenleri gibi içine veya dışına bir DLL (DLL sınırı arasında işlev çağrıları), DLL içine çağırmak dosyaları yanı sıra, DLL farklı kopyalarını kullanırsanız beklenmeyen davranış oluşabilir nesneleri CRT kitaplığı.

Bellek ayırma ilgili bir sorun meydana gelebilir (açıkça ile `new` veya `malloc`, veya örtük olarak `strdup`, `strstreambuf::str`, vb.) ve ardından bir işaretçi serbest bırakılacak bir DLL sınırında geçirin. DLL ve onun kullanıcıları farklı kopyalara CRT kitaplık kullanıyorsanız, bu bellek erişim ihlali veya yığın bozulması neden olabilir.

Bu sorunun başka bir belirti gibi hata ayıklama sırasında çıktı penceresinde bir hata olabilir:

YIĞIN []: Geçersiz adres için RtlValidateHeap(#,#) belirtildi

## <a name="causes"></a>Nedenler

CRT kitaplığının her kopyası uygulamanıza veya DLL tarafından iş parçacığı yerel depolama alanında tutulur ayrı ve farklı bir durum vardır. Bu nedenle, ortam değişkenleri, dosya tanıtıcıları gibi CRT nesnelerini ve yerel ayarlar yalnızca uygulamadaki CRT veya bu nesneler burada ayrılan veya ayarlayın DLL kopyası için geçerli olur. Bir DLL ve uygulama istemcileri farklı kopyalarını CRT kitaplığı kullandığınızda, bu CRT nesnelerini DLL sınırında geçirmek ve bunları diğer tarafta doğru işlenmek üzere beklediğiniz olamaz. Bu, özellikle CRT sürümlerinden önce Evrensel CRT Visual Studio 2015 ve sonraki sürümlerde geçerlidir. Visual C++ 2013 veya daha önce oluşturulan Visual Studio'nun her sürümü için sürüme özgü bir CRT kitaplığı vardı. Örneğin, kendi veri yapıları ve adlandırma kuralları, CRT iç uygulama ayrıntıları her sürümde farklı. CRT CRT dll'nin farklı bir sürüme bir sürümü için derlenmiş kod dinamik olarak bağlama hiçbir zaman desteklenen, ancak zaman zaman, daha fazla Şanslar tasarıma göre çalışır.

Ayrıca, kendi yığını Yöneticisi CRT kitaplığının her kopyası olduğundan, bir CRT Kitaplığı'nda Bellek ayırma ve farklı bir kopyasını CRT kitaplığı tarafından serbest bırakılacak bir DLL sınırı arasında işaretçi işleve yığın bozulma olası bir nedeni vardır. CRT nesnelerini sınırında geçirir veya bellek ayırırken ve DLL dışında serbest bırakılacak bekler, DLL dosyanızı tasarlarken, uygulama istemcilerinin aynı kopyasını CRT kitaplığının DLL olarak kullanmak için dll kısıtlayın. Normalde yalnızca her ikisi de aynı sürüme CRT DLL yükleme zamanında bağlıysa DLL ve istemcileri CRT kitaplığı aynı kopyasını kullanın. Visual Studio 2015 ve daha sonra Windows 10 tarafından kullanılan Evrensel CRT kitaplığının DLL sürümü artık merkezi olarak dağıtılan bir Windows bileşeni olduğundan, ucrtbase.dll olduğu aynı Visual Studio 2015 ve sonraki sürümleri ile oluşturulan uygulamalar için. Ancak, hatta CRT kodu aynı olduğunda, farklı bir yığın kullanan bileşen için bir yığında ayrılan bellek kapalı el olamaz.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Bu örnek, bir DLL sınırında bir dosya tanıtıcısı geçirir.

DLL ve .exe dosyası paylaştıkları CRT tek bir kopyasını dolayısıyla /MD ile oluşturulur.

CRT ayrı bir kopyasını kullanmasını sağlayarak/MT ile yeniden oluşturursanız, sonuçta elde edilen test1Main.exe sonuçları bir erişim ihlali ile çalışıyor.

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

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Bu örnek, bir DLL sınırında ortam değişkenlerini geçirir.

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

CRT yalnızca bir kopyasını kullanılmasını sağlamak amacıyla DLL ve .exe dosyası ile /MD oluşturulur, program başarıyla çalıştırır ve aşağıdaki çıktıyı üretir:

```
New MYLIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>Ayrıca bkz.

[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)
