---
title: _cwait
ms.date: 11/04/2016
apiname:
- _cwait
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _cwait
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
ms.openlocfilehash: f356afc91f794753f12b5b673c609ef03fbaa5ec
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69499969"
---
# <a name="_cwait"></a>_cwait

Başka bir işlem sonlanana kadar bekler.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _cwait(
   int *termstat,
   intptr_t procHandle,
   int action
);
```

### <a name="parameters"></a>Parametreler

*termstat*<br/>
Belirtilen işlemin sonuç kodunun depolanacağı veya **null**olacağı bir arabelleğin işaretçisi.

*procHandle*<br/>
Beklenecek işlemin tanıtıcısı (yani, **_cwait** 'in dönmesi için sonlandırılması gereken işlem).

*ön*<br/>
NULL: Windows işletim sistemi uygulamaları tarafından yoksayıldı; diğer uygulamalar için: *procHandle*üzerinde gerçekleştirilecek eylem kodu.

## <a name="return-value"></a>Dönüş Değeri

Belirtilen işlem başarıyla tamamlandığında, belirtilen işlemin tanıtıcısını döndürür ve *termstat* belirtilen işlem tarafından döndürülen sonuç koduna ayarlanır. Aksi takdirde,-1 döndürür ve **errno** değerini aşağıdaki şekilde ayarlar.

|Değer|Açıklama|
|-----------|-----------------|
|**ECHILD**|Belirtilen işlem yok, *procHandle* geçersiz veya [GetExitCodeProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess) veya [WaitForSingleObject](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject) API çağrısı başarısız oldu.|
|**EINVAL**|*eylem* geçersiz.|

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Cwait** Işlevi, *procHandle*tarafından sunulan belirtilen işlemin işlem kimliği sonlandırmasını bekler. **_Cwait** öğesine geçirilen *procHandle* değeri, belirtilen işlemi oluşturan [_üretme](../../c-runtime-library/spawn-wspawn-functions.md) işlevine yapılan çağrı tarafından döndürülen değer olmalıdır. İşlem KIMLIĞI **_cwait** çağrılmadan önce sonlandığında, **_cwait** hemen döndürülür. **_cwait** , geçerli bir tanıtıcı (*procHandle*) var olan herhangi bir bilinen işlemi beklemek için herhangi bir işlem tarafından kullanılabilir.

*termstat* , belirtilen işlemin dönüş kodunun depolanacağı bir arabelleğe işaret eder. *Termstat* değeri, belirtilen işlemin normal olarak Windows [ExitProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitprocess) API 'sini çağırarak sonlandırılıp sonlandırılmadığını gösterir. Belirtilen işlem **Çıkış** veya **_çıkış**çağırırsa, **Main**'ten geri döndüğünde veya **Main**'in sonuna ulaştığında **ExitProcess** dahili olarak çağrılır. *Termstat*üzerinden geri geçirilen değer hakkında daha fazla bilgi için bkz. [GetExitCodeProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess). **_Cwait** , *termstat*için **null** değer kullanılarak çağrılırsa, belirtilen işlemin dönüş kodu depolanmaz.

Bu ortamlarda üst-alt ilişkileri uygulanmadığından, *eylem* parametresi Windows işletim sistemi tarafından yok sayılır.

*ProcHandle* -1 veya-2 olmadığı sürece (geçerli işlem veya iş parçacığına yönelik Tanıtıcılarda), tanıtıcı kapatılacak. Bu nedenle, bu durumda döndürülen tanıtıcıyı kullanmayın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_cwait**|\<Process. h >|\<errno. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_cwait.c
// compile with: /c
// This program launches several processes and waits
// for a specified process to finish.

#define _CRT_RAND_S

#include <windows.h>
#include <process.h>
#include <stdlib.h>
#include <stdio.h>
#include <time.h>

// Macro to get a random integer within a specified range
#define getrandom( min, max ) (( (rand_s (&number), number) % (int)((( max ) + 1 ) - ( min ))) + ( min ))

struct PROCESS
{
   int     nPid;
   char    name[40];
} process[4] = { { 0, "Ann" }, { 0, "Beth" }, { 0, "Carl" }, { 0, "Dave" } };

int main( int argc, char *argv[] )
{
   int termstat, c;
   unsigned int number;

   srand( (unsigned)time( NULL ) );    // Seed randomizer

   // If no arguments, this is the calling process
   if ( argc == 1 )
   {
      // Spawn processes in numeric order
      for ( c = 0; c < 4; c++ ) {
         _flushall();
         process[c].nPid = _spawnl( _P_NOWAIT, argv[0], argv[0],
                                    process[c].name, NULL );
      }

      // Wait for randomly specified process, and respond when done
      c = getrandom( 0, 3 );
      printf( "Come here, %s.\n", process[c].name );
      _cwait( &termstat, process[c].nPid, _WAIT_CHILD );
      printf( "Thank you, %s.\n", process[c].name );

   }
   // If there are arguments, this must be a spawned process
   else
   {
      // Delay for a period that's determined by process number
      Sleep( (argv[1][0] - 'A' + 1) * 1000L );
      printf( "Hi, Dad. It's %s.\n", argv[1] );
   }
}
```

```Output
Hi, Dad. It's Ann.
Come here, Ann.
Thank you, Ann.
Hi, Dad. It's Beth.
Hi, Dad. It's Carl.
Hi, Dad. It's Dave.
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
