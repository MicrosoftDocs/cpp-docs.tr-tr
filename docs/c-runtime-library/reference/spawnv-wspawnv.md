---
title: _spawnv, _wspawnv
ms.date: 4/2/2020
api_name:
- _wspawnv
- _spawnv
- _o__spawnv
- _o__wspawnv
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
- wspawnv
- _spawnv
- _wspawnv
helpviewer_keywords:
- wspawnv function
- processes, creating
- _spawnv function
- processes, executing new
- process creation
- _wspawnv function
- spawnv function
ms.assetid: 72360ef4-dfa9-44c1-88c1-b3ecb660aa7d
ms.openlocfilehash: f4a4d695e265c28efd1b9da8588752d8b2635163
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355889"
---
# <a name="_spawnv-_wspawnv"></a>_spawnv, _wspawnv

Yeni bir işlem oluşturur ve yürütür.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _spawnv(
   int mode,
   const char *cmdname,
   const char *const *argv
);
intptr_t _wspawnv(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv
);
```

### <a name="parameters"></a>Parametreler

*Modu*<br/>
Arama işlemi için yürütme modu.

*Cmdname*<br/>
Yürütülecek dosyanın yolu.

*Argv*<br/>
Bağımsız değişkenler için işaretçiler dizisi. Argüman *argv*[0] genellikle gerçek modda bir yol veya korumalı modda program adı için bir işaretçi ve *argv*[1] *argv***[n]** ile yeni bağımsız değişken listesi oluşturan karakter dizeleri işaretçileri vardır. Bağımsız değişken *argv*[**n** +1] bağımsız değişken listesinin sonunu işaretlemek için bir **NULL** işaretçisi olmalıdır.

## <a name="return-value"></a>Dönüş Değeri

Senkron **_spawnv** veya **_wspawnv** *(mod*için belirtilen **_P_WAIT)** gelen dönüş değeri, yeni işlemin çıkış durumudur. Bir senkron **_spawnv** veya **_wspawnv** *(mod*için belirtilen **_P_NOWAIT** veya **_P_NOWAITO)** gelen dönüş değeri işlem koludur. İşlem normal olarak sonlandırılırsa çıkış durumu 0'dır. Oluşturulan işlem özellikle çıkış **yordamını** sıfır olmayan bir bağımsız değişkenle çağırıyorsa, çıkış durumunu sıfır olmayan bir değere ayarlayabilirsiniz. Yeni işlem açıkça olumlu bir çıkış durumu ayarlamadıysa, pozitif çıkış durumu iptal veya kesme ile anormal bir çıkış gösterir. -1'in geri dönüş değeri bir hatayı gösterir (yeni işlem başlatılmadı). Bu durumda, **errno** aşağıdaki değerlerden birine ayarlanır.

|||
|-|-|
| **E2BIG** | Bağımsız değişken listesi 1024 baytı aşıyor. |
| **Eınval** | mod bağımsız *değişkeni* geçersizdir. |
| **Enoent** | Dosya veya yol bulunamadı. |
| **ENOEXEC** | Belirtilen dosya yürütülemez veya geçersiz yürütülebilir dosya biçimine sahiptir. |
| **ENOMEM** | Yeni işlemi yürütmek için yeterli bellek kullanılabilir. |

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, komut satırı bağımsız değişkenlerine bir dizi işaretçi geçirerek yeni bir işlem oluşturur ve yürütür.

Bu işlevler parametrelerini doğrular. *Cmdname* veya *argv* null işaretçisi ise veya *argv* null işaretçiye işaret ediyorsa veya *argv*[0] boş bir dize ise, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **EINVAL** **için errno** ayarlayın ve -1 döndürün. Yeni bir süreç ortaya çıkarılamaz.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_spawnv**|\<stdio.h> \<veya process.h>|
|**_wspawnv**|\<stdio.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

_spawn, [_wspawn İşlevler'deki](../../c-runtime-library/spawn-wspawn-functions.md)örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[Iptal](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec Fonksiyonlar](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
