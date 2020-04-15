---
title: _execv, _wexecv
ms.date: 4/2/2020
api_name:
- _wexecv
- _execv
- _o__execv
- _o__wexecv
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
- _execv
- _wexecv
- wexecv
helpviewer_keywords:
- _wexecv function
- _execv function
- wexecv function
- execv function
ms.assetid: 8dbaf7bc-9040-4316-a0c1-db7e866b52af
ms.openlocfilehash: 638364afa75fa1b04b598370473dee48964c5763
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347897"
---
# <a name="_execv-_wexecv"></a>_execv, _wexecv

Yeni alt işlemleri yükler ve yürütür.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _execv(
   const char *cmdname,
   const char *const *argv
);
intptr_t _wexecv(
   const wchar_t *cmdname,
   const wchar_t *const *argv
);
```

### <a name="parameters"></a>Parametreler

*Cmdname*<br/>
Dosyanın yürütülme yolu.

*Argv*<br/>
Parametrelere işaretçiler dizisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevler arama işlemine dönmez. -1'in geri dönüş değeri bir hatayı gösterir ve bu durumda **errno** global değişkeni ayarlanır.

|**errno** değeri|Açıklama|
|-------------------|-----------------|
|**E2BIG**|Bağımsız değişkenler ve ortam ayarları için gereken alan 32 KB'yi aşıyor.|
|**EACCES**|Belirtilen dosyada kilitleme veya paylaşma ihlali vardır.|
|**Eınval**|Geçersiz parametre.|
|**EMFILE**|Çok fazla dosya açık (belirtilen dosya yürütülebilir olup olmadığını belirlemek için açılmalıdır).|
|**Enoent**|Dosya veya yol bulunamadı.|
|**ENOEXEC**|Belirtilen dosya yürütülemez veya geçersiz yürütülebilir dosya biçimine sahiptir.|
|**ENOMEM**|Yeni işlemi yürütmek için yeterli bellek kullanılabilir değildir; kullanılabilir bellek bozuldu; veya arama işleminin düzgün ayrılmadığını belirten geçersiz bir blok vardır.|

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, komut satırı bağımsız değişkenlerine bir dizi işaretçi geçirerek yeni bir işlem yükler ve yürütür.

_execv **_execv** işlevleri parametrelerini doğrular. *cmdname* null işaretçisi ise veya *argv* null işaretçisiyse, boş bir diziişaretçisiyse veya dizi ilk bağımsız değişken olarak boş bir dize içeriyorsa, **_execv** işlevleri [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, bu işlevler **EINVAL** ve return -1 **için errno** ayarlayın. Hiçbir işlem başlatılmadı.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|
|--------------|---------------------|---------------------|
|**_execv**|\<process.h>|\<errno.h>|
|**_wexecv**|\<process.h> \<veya wchar.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

_exec, [_wexec İşlevler'deki](../../c-runtime-library/exec-wexec-functions.md)örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, _wexec Fonksiyonlar](../../c-runtime-library/exec-wexec-functions.md)<br/>
[Iptal](abort.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
