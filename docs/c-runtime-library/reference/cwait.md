---
title: _cwait
ms.date: 4/2/2020
api_name:
- _cwait
- _o__cwait
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _cwait
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
ms.openlocfilehash: d54f62c8ce391b2c8ead92a0a73ac48e6f2b3cb3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348158"
---
# <a name="_cwait"></a>_cwait

Başka bir işlem sona erene kadar bekler.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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
Belirtilen işlemin sonuç kodunun depolandığı bir arabelleğe işaretçi veya **NULL**.

*procHandle*<br/>
Bekletmek için işlem için tutamaç (diğer bir süre **önce _cwait** dönebilen sonlandırmak zorunda olan işlem).

*Eylem*<br/>
NULL: Windows işletim sistemi uygulamaları tarafından göz ardı; diğer uygulamalar için: *procHandle*gerçekleştirmek için eylem kodu .

## <a name="return-value"></a>Dönüş Değeri

Belirtilen işlem başarıyla tamamlandığında, belirtilen işlemin tutamacını döndürür ve *termstat'ı* belirtilen işlem tarafından döndürülen sonuç koduna ayarlar. Aksi takdirde, -1 döndürür ve aşağıdaki gibi **errno** ayarlar.

|Değer|Açıklama|
|-----------|-----------------|
|**ECHILD**|Belirtilen bir işlem yok, *procHandle* geçersiz veya [GetExitCodeProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess) veya [WaitForSingleObject](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject) API'ye yapılan çağrı başarısız oldu.|
|**Eınval**|*eylem* geçersizdir.|

Bu ve diğer iade kodları hakkında daha fazla bilgi için [errno, _doserrno, _sys_errlist ve _sys_nerr'a](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**_cwait** işlevi *procHandle*tarafından sağlanan belirtilen işlemin işlem kimliğinin sonlandırılması için bekler. **_cwait** geçirilen *procHandle* değeri, belirtilen işlemi oluşturan [_spawn](../../c-runtime-library/spawn-wspawn-functions.md) işlevine çağrı yla döndürülen değer olmalıdır. İşlem kimliği **_cwait** çağrılmadan önce sona ererse, **_cwait** hemen geri döner. **_cwait,** geçerli bir tutamacın *(procHandle)* bulunduğu bilinen diğer herhangi bir işlemi beklemek için herhangi bir işlem tarafından kullanılabilir.

*termstat,* belirtilen işlemin dönüş kodunun depolanacağı bir arabelleğe işaret ediyor. *Termstat* değeri, belirtilen işlemin Windows [ExitProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitprocess) API'sini arayarak normal olarak sonlandırılıp sonlandırılmadığını gösterir. **ExitProcess,** belirtilen işlem **çıkış** veya **_exit**çağırırsa dahili olarak çağrılır, ana dan döner veya **ana**işlemin sonuna ulaşır. **main** *Termstat'tan*aktarılan değer hakkında daha fazla bilgi için [GetExitCodeProcess'e](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess)bakın. **_cwait** *termstat*için **NULL** değeri kullanılarak çağrılırsa, belirtilen işlemin iade kodu depolanmaz.

Üst-alt ilişkileri bu ortamlarda *uygulanmadığından, eylem* parametresi Windows işletim sistemi tarafından yoksayılır.

*ProcHandle* -1 veya -2 (geçerli işlem veya iş parçacığı için kolları) olmadığı sürece, tutamaç kapatılır. Bu nedenle, bu durumda, döndürülen tutamacı kullanmayın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_cwait**|\<process.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
