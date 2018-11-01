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
ms.openlocfilehash: f7a49497ac71ec15261e1215bd2bbed2e49f42ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489628"
---
# <a name="cwait"></a>_cwait

Başka bir işlem sonlanana kadar bekler.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Belirtilen işlem Sonuç kodu depolanacağı, arabellek için işaretçi veya **NULL**.

*procHandle*<br/>
Üzerinde beklenilen bir işlem tanıtıcısı (diğer bir deyişle, önce sonlandırmak için olan işlem **_cwait** dönebilirsiniz).

*Eylem*<br/>
NULL: Windows işletim sistemi uygulamalar tarafından yok sayılır; diğer uygulamalar için: üzerinde gerçekleştirmek için eylem kod *procHandle*.

## <a name="return-value"></a>Dönüş Değeri

Belirtilen işlem başarıyla tamamlandığında, belirtilen işlem tanıtıcısını döndürür ve ayarlar *termstat* için belirtilen işlem tarafından döndürülen sonuç kodu. Aksi takdirde, -1 döndürür ve ayarlar **errno** gibi.

|Değer|Açıklama|
|-----------|-----------------|
|**ECHILD**|Belirtilen işlem mevcut, *procHandle* geçersiz veya çağrı [GetExitCodeProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess) veya [WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject) API'si başarısız oldu.|
|**EINVAL**|*Eylem* geçersiz.|

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Cwait** işlevi tarafından sağlanan işlem kimliği belirtilen işlemin sonlandırılmasını bekler *procHandle*. Değerini *procHandle* yapan **_cwait** çağrısı tarafından döndürülen değer olmalıdır [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) belirtilen işlemi oluşturan bir işlev. İşlem kimliği önce sona ererse **_cwait** çağrıldığında **_cwait** hemen döndürür. **_cwait** kendisi için başka bilinen işlem için beklenecek herhangi bir işlem tarafından kullanılan geçerli bir tanıtıcı (*procHandle*) bulunmaktadır.

*termstat* belirtilen işlemin dönüş kodu depolanacağı bir arabelleğe işaret eder. Değerini *termstat* belirtilen işlemi normalde Windows çağırarak sonlandırıldı olup olmadığını gösteren [ExitProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitprocess) API. **ExitProcess** belirtilen işlem çağırırsa dahili olarak adlandırılır **çıkmak** veya **_exit**, döndürür **ana**, veya sonuna ulaştığında **ana** . Geriye doğru geçirilen değeri hakkında daha fazla bilgi için *termstat*, bkz: [GetExitCodeProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess). Varsa **_cwait** kullanılarak çağrılan bir **NULL** değerini *termstat*, belirli bir işlemin dönüş kodu depolanmaz.

*Eylem* parametresi, Windows işletim sistemi tarafından alınmaz, çünkü bu ortamlarda üst-alt ilişkileri uygulanmaz.

Sürece *procHandle* -1 -2 mi (geçerli işlem ya da iş parçacığı işliyor), tanıtıcı kapatılacak. Bu nedenle, bu durumda, döndürülen tanıtıcının kullanmayın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_cwait**|\<Process.h >|\<errno.h >|

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
