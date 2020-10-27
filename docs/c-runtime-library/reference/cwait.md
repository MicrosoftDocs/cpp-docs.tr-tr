---
title: _cwait
description: Microsoft Visual C Runtime işlevi için API başvurusu `_cwait()` .
ms.date: 10/23/2020
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 5b4c4db3c40645b947583b722d345c2e80dcaa8e
ms.sourcegitcommit: faecabcdd12ff53eb79dc0df193fc3567f2f037c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92639113"
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

*`termstat`*\
Belirtilen işlemin sonuç kodunun depolanacağı bir arabelleğin işaretçisi **`NULL`** .

*`procHandle`*\
Beklenecek işlemin tanıtıcısı (yani, **_cwait** önce sonlanacak işlem).

*`action`*\
**`NULL`** : Windows işletim sistemi uygulamaları tarafından yoksayıldı; diğer uygulamalar için: üzerinde gerçekleştirilecek eylem kodu *`procHandle`* .

## <a name="return-value"></a>Dönüş Değeri

Belirtilen işlem başarıyla tamamlandığında, belirtilen işlemin tanıtıcısını döndürür ve *`termstat`* belirtilen işlem tarafından döndürülen sonuç koduna ayarlanır. Aksi takdirde,-1 döndürür ve **`errno`** aşağıdaki gibi ayarlar.

|Değer|Açıklama|
|-----------|-----------------|
|**`ECHILD`**|Belirtilen işlem yok, *`procHandle`* geçersiz veya [`GetExitCodeProcess`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess) API çağrısı [`WaitForSingleObject`](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject) başarısız oldu.|
|**`EINVAL`**|*`action`* geçersiz.|

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz [`errno, _doserrno, _sys_errlist, and _sys_nerr`](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ..

## <a name="remarks"></a>Açıklamalar

**`_cwait`** İşlevi, tarafından sağlanmış belirtilen işlemin Işlem kimliği sonlandırmasını bekler *`procHandle`* . Geçirilen değeri, *`procHandle`* **`_cwait`** [`_spawn`](../../c-runtime-library/spawn-wspawn-functions.md) belirtilen işlemi oluşturan işleve yapılan çağrı tarafından döndürülen değer olmalıdır. İşlem KIMLIĞI çağrılmadan önce sonlandığında **`_cwait`** , **`_cwait`** hemen döndürür. **`_cwait`** , geçerli bir tanıtıcı () var olan herhangi bir bilinen işlemi beklemek için herhangi bir işlem tarafından kullanılabilir *`procHandle`* .

*`termstat`* belirtilen işlemin dönüş kodunun depolanacağı bir arabelleği işaret eder. Değeri, *`termstat`* belirtilen işlemin normal olarak Windows API 'sini çağırarak sonlandırılıp sonlandırılmadığını gösterir [`ExitProcess`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitprocess) . **`ExitProcess`** Belirtilen işlem çağırıyorsa **`exit`** veya **`_exit`** **`main`** sonuna geldiğinde veya sonuna ulaştığında dahili olarak çağrılır **`main`** . Üzerinden geri geçirilen değer hakkında daha fazla bilgi için *`termstat`* bkz. [GetExitCodeProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess). **`_cwait`** İçin bir değer kullanılarak çağrılırsa **`NULL`** *`termstat`* , belirtilen işlemin dönüş kodu depolanmaz.

*`action`* Bu ortamlarda üst-alt ilişkileri uygulanmadığından, parametre Windows işletim sistemi tarafından yok sayılır.

*`procHandle`* -1 veya-2 olmadığı sürece (geçerli işlem veya iş parçacığı için tanıtıcı), tanıtıcı kapatılacak. Bu durumda, döndürülen tanıtıcıyı kullanmayın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**`_cwait`**|\<process.h>|\<errno.h>|

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
    intptr_t hProcess;
    char    name[40];
} process[4] = { { 0, "Ann" }, { 0, "Beth" }, { 0, "Carl" }, { 0, "Dave" } };

int main(int argc, char* argv[])
{
    int termstat, c;
    unsigned int number;

    srand((unsigned)time(NULL));    // Seed randomizer

    // If no arguments, this is the calling process
    if (argc == 1)
    {
        // Spawn processes in numeric order
        for (c = 0; c < 4; c++) {
            _flushall();
            process[c].hProcess = _spawnl(_P_NOWAIT, argv[0], argv[0],
                process[c].name, NULL);
        }

        // Wait for randomly specified process, and respond when done
        c = getrandom(0, 3);
        printf("Come here, %s.\n", process[c].name);
        _cwait(&termstat, process[c].hProcess, _WAIT_CHILD);
        printf("Thank you, %s.\n", process[c].name);

    }
    // If there are arguments, this must be a spawned process
    else
    {
        // Delay for a period that's determined by process number
        Sleep((argv[1][0] - 'A' + 1) * 1000L);
        printf("Hi, Dad. It's %s.\n", argv[1]);
    }
}
```

Çıktının sırası çalışma durumundan çalışacak şekilde değişir.

```Output
Hi, Dad. It's Ann.
Come here, Ann.
Thank you, Ann.
Hi, Dad. It's Beth.
Hi, Dad. It's Carl.
Hi, Dad. It's Dave.
```

## <a name="see-also"></a>Ayrıca bkz.

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)\
[_spawn, _wspawn Işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)
