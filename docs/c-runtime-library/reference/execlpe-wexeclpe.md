---
title: _execlpe, _wexeclpe
ms.date: 11/04/2016
apiname:
- _execlpe
- _wexeclpe
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
- _wexeclpe
- execlpe
- wexeclpe
- _execlpe
helpviewer_keywords:
- wexeclpe function
- _wexeclpe function
- _execlpe function
- execlpe function
ms.assetid: 07b861da-3e7e-4f1d-bb80-ad69b55e5162
ms.openlocfilehash: e3aa4189d2a384a0092c742909e97c5efc52b5ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339370"
---
# <a name="execlpe-wexeclpe"></a>_execlpe, _wexeclpe

Yükler ve yeni alt işlemleri yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _execlpe(
   const char *cmdname,
   const char *arg0,
   ... const char *argn,
   NULL,
   const char *const *envp
);
intptr_t _wexeclpe(
   const wchar_t *cmdname,
   const wchar_t *arg0,
   ... const wchar_t *argn,
   NULL,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>Parametreler

*■ CmdName*<br/>
Yürütülecek dosyanın yolu.

*arg0*,... *argn*<br/>
Parametreler için işaretçiler listesi.

*envp*<br/>
Ortam ayarlarına bir işaretçiler dizisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevler çağırma işlemine geri gitmez. -1 değeri, bu durumda bir hata belirtir **errno** global değişkeni ayarlanır.

|**errno** değeri|Açıklama|
|-------------------|-----------------|
|**E2BIG**|Bağımsız değişkenler ve ortam ayarları için gereken alan 32 KB aşıyor.|
|**SPAWN**|Belirtilen dosya kilitleme veya paylaşma ihlali var.|
|**EINVAL**|Geçersiz parametre.|
|**EMFILE**|Çok fazla dosya açık (belirtilen dosyanın yürütülebilir olup olmadığını belirlemek için açılması gerekir).|
|**ENOENT**|Dosya veya yol bulunamadı.|
|**ENOEXEC**|Belirtilen dosya yürütülebilir değil veya geçersiz bir yürütülebilir dosya biçimine sahip.|
|**ENOMEM**|Yeni işlemi yürütmek yeterli bellek yok; kullanılabilir bellek bozulmuş; veya, çağırma işlemi düzgün ayrılmamış olduğunu belirten geçersiz bir engel var.|

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, yükler ve her komut satırı bağımsız değişkenini ayrı bir parametre geçirerek ve ayrıca bir işaretçiler dizisini ortam ayarlarına geçirerek yeni bir işlem yürütür. Bu işlevleri **yolu** yürütülecek dosyayı bulmak için ortam değişkeni.

**_Execlpe** işlevleri kendi parametrelerini doğrular. Ya da *■ cmdname* veya *arg0* null işaretçileri ya da boş dizeyse bu işlevler çağırma açıklandığı gibi geçersiz parametre işleyicisi [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür. Yeni bir işlem başlatılır.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**_execlpe**|\<Process.h >|\<errno.h >|
|**_wexeclpe**|\<Process.h > veya \<wchar.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örnekte bakın [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
