---
title: _spawnve, _wspawnve
ms.date: 4/2/2020
api_name:
- _spawnve
- _wspawnve
- _o__spawnve
- _o__wspawnve
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
- wspawnve
- _spawnve
- _wspawnve
helpviewer_keywords:
- _spawnve function
- spawnve function
- wspawnve function
- processes, creating
- _wspawnve function
- processes, executing new
- process creation
ms.assetid: 26d1713d-b551-4f21-a07b-e9891a2ae6cf
ms.openlocfilehash: 0f546185039bb1503af40d5f690fd8d8c172a679
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355867"
---
# <a name="_spawnve-_wspawnve"></a>_spawnve, _wspawnve

Yeni bir işlem oluşturur ve yürütür.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _spawnve(
   int mode,
   const char *cmdname,
   const char *const *argv,
   const char *const *envp
);
intptr_t _wspawnve(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>Parametreler

*Modu*<br/>
Arama işlemi için yürütme modu.

*Cmdname*<br/>
Yürütülecek dosyanın yolu.

*Argv*<br/>
Bağımsız değişkenler için işaretçiler dizisi. Argüman *argv*[0] genellikle gerçek modda bir yol veya korumalı modda program adı için bir işaretçi ve *argv*[1] *argv***[n]** ile yeni bağımsız değişken listesi oluşturan karakter dizeleri işaretçileri vardır. Bağımsız değişken *argv*[**n** +1] bağımsız değişken listesinin sonunu işaretlemek için bir **NULL** işaretçisi olmalıdır.

*Envp*<br/>
Ortam ayarlarına işaretçiler dizisi.

## <a name="return-value"></a>Dönüş Değeri

Senkron **_spawnve** veya **_wspawnve** *(mod*için belirtilen **_P_WAIT)** gelen dönüş değeri, yeni işlemin çıkış durumudur. Bir eşzamanlı **_spawnve** veya **_wspawnve** *(mod*için belirtilen **_P_NOWAIT** veya **_P_NOWAITO)** gelen dönüş değeri işlem koludur. İşlem normal olarak sonlandırılırsa çıkış durumu 0'dır. Oluşturulan işlem özellikle çıkış **yordamını** sıfır olmayan bir bağımsız değişkenle çağırıyorsa, çıkış durumunu sıfır olmayan bir değere ayarlayabilirsiniz. Yeni işlem açıkça olumlu bir çıkış durumu ayarlamadıysa, pozitif çıkış durumu iptal veya kesme ile anormal bir çıkış gösterir. -1'in geri dönüş değeri bir hatayı gösterir (yeni işlem başlatılmadı). Bu durumda, **errno** aşağıdaki değerlerden birine ayarlanır.

|||
|-|-|
| **E2BIG** | Bağımsız değişken listesi 1024 baytı aşıyor. |
| **Eınval** | mod bağımsız *değişkeni* geçersizdir. |
| **Enoent** | Dosya veya yol bulunamadı. |
| **ENOEXEC** | Belirtilen dosya yürütülemez veya geçersiz yürütülebilir dosya biçimine sahiptir. |
| **ENOMEM** | Yeni işlemi yürütmek için yeterli bellek kullanılabilir. |

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, komut satırı bağımsız değişkenlerine bir dizi işaretçi ve ortam ayarlarına bir dizi işaretçi geçirerek yeni bir işlem oluşturur ve yürütür.

Bu işlevler parametrelerini doğrular. *Cmdname* veya *argv* null işaretçisi ise veya *argv* null işaretçiye işaret ediyorsa veya *argv*[0] boş bir dize ise, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **EINVAL** **için errno** ayarlayın ve -1 döndürün. Yeni bir süreç ortaya çıkarılamaz.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_spawnve**|\<stdio.h> \<veya process.h>|
|**_wspawnve**|\<stdio.h> \<veya wchar.h>|

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
