---
description: 'Hakkında daha fazla bilgi edinin: _spawnlp _wspawnlp'
title: _spawnlp, _wspawnlp
ms.date: 11/04/2016
api_name:
- _wspawnlp
- _spawnlp
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wspawnlp
- wspawnlp
- _spawnlp
helpviewer_keywords:
- wspawnlp function
- _spawnlp function
- processes, creating
- processes, executing new
- _wspawnlp function
- process creation
- spawnlp function
ms.assetid: 74fc6e7a-4f24-4103-9387-7177875875e6
ms.openlocfilehash: bdeccf2fd1880158a2db7ab0f6ab03194ed42d97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292487"
---
# <a name="_spawnlp-_wspawnlp"></a>_spawnlp, _wspawnlp

Yeni bir işlem oluşturur ve yürütür.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _spawnlp(
   int mode,
   const char *cmdname,
   const char *arg0,
   const char *arg1,
   ... const char *argn,
   NULL
);
intptr_t _wspawnlp(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *arg0,
   const wchar_t *arg1,
   ... const wchar_t *argn,
   NULL
);
```

### <a name="parameters"></a>Parametreler

*modundaysa*<br/>
Çağırma işlemi için yürütme modu.

*cmdname*<br/>
Yürütülecek dosyanın yolu.

*arg0*, *arg1*,... *argN*<br/>
Bağımsız değişkenlere işaretçiler listesi. *Arg0* bağımsız değişkeni genellikle bir *cmdname* işaretçisi olur. *ArgN* aracılığıyla *arg1* bağımsız değişkenleri, yeni bağımsız değişken listesini oluşturan karakter dizelerinin işaretçileridir. Aşağıdaki *argN*, bağımsız değişken listesinin sonunu Işaretlemek için **null** bir işaretçi olmalıdır.

## <a name="return-value"></a>Dönüş Değeri

Zaman uyumlu bir **_spawnlp** veya **_wspawnlp** ( *mod* için belirtilen **_P_WAIT** ) dönüş değeri, yeni işlemin çıkış durumudur. Zaman uyumsuz bir **_spawnlp** veya **_wspawnlp** (**_P_NOWAIT** veya *mod* için belirtilen **_P_NOWAITO** ) dönüş değeri işlem tanıtıcıdır. İşlem normal şekilde sonlandırılırsa çıkış durumu 0 ' dır. Oluşturulan işlem özellikle **Çıkış** yordamını sıfır dışında bir bağımsız değişkenle çağırırsa çıkış durumunu sıfır dışında bir değere ayarlayabilirsiniz. Yeni işlem açıkça pozitif bir çıkış durumu ayarlanmamışsa, bir pozitif çıkış durumu, bir iptal veya kesme ile olağan dışı bir çıkış olduğunu gösterir. -1 ' in dönüş değeri bir hatayı gösterir (yeni işlem başlatılmaz). Bu durumda, **errno** aşağıdaki değerlerden birine ayarlanır.

| Değer | Açıklama |
|-|-|
| **E2BIG** | Bağımsız değişken listesi 1024 baytı aşıyor. |
| **EıNVAL** | *Mode* bağımsız değişkeni geçersiz. |
| **ENOENT** | Dosya veya yol bulunamadı. |
| **ENOEXEC** | Belirtilen dosya yürütülebilir değil veya geçersiz yürütülebilir dosya biçimine sahip. |
| **ENOMEM** | Yeni işlemi yürütmek için yeterli kullanılabilir bellek yok. |

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, her komut satırı bağımsız değişkenini ayrı bir parametre olarak geçirerek ve yürütülecek dosyayı bulmak için **Path** ortam değişkenini kullanarak yeni bir işlem oluşturur ve yürütür.

Bu işlevler, parametrelerini doğrular. Herhangi bir *cmdname* veya *arg0* boş bir dize veya null işaretçisiyse, bu işlevler [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklanan şekilde geçersiz bir parametre özel durumu oluşturur. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** ' ı **EINVAL** olarak ayarlar ve-1 döndürür. Yeni işlem oluşturulmadı.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_spawnlp**|\<process.h>|
|**_wspawnlp**|\<stdio.h> veya \<wchar.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Spawn, _Wspawn işlevlerde](../../c-runtime-library/spawn-wspawn-functions.md)örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn, _wspawn Işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[durdur](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec Işlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
