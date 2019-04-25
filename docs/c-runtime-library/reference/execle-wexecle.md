---
title: _execle, _wexecle
ms.date: 11/04/2016
apiname:
- _execle
- _wexecle
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
- wexecle
- _execle
- _wexecle
helpviewer_keywords:
- wexecle function
- execle function
- _wexecle function
- _execle function
ms.assetid: 75efa9c5-96b7-4e23-acab-06258901f63a
ms.openlocfilehash: dbd84dd8d8e150a063dad4dc89a572c317bce544
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288168"
---
# <a name="execle-wexecle"></a>_execle, _wexecle

Yükler ve yeni alt işlemleri yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _execle(
   const char *cmdname,
   const char *arg0,
   ... const char *argn,
   NULL,
   const char *const *envp
);
intptr_t _wexecle(
   const wchar_t *cmdname,
   const wchar_t *arg0,
   ... const wchar_t *argn,
   NULL,
   const char *const *envp
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
|**EMFILE**|Çok fazla dosya açık durumda. (Belirtilen dosyanın yürütülebilir olup olmadığını belirlemek için açık olması gerekir.)|
|**ENOENT**|Dosya veya yol bulunamadı.|
|**ENOEXEC**|Belirtilen dosya yürütülebilir değil veya geçersiz bir yürütülebilir dosya biçimine sahip.|
|**ENOMEM**|Yeni işlemi yürütmek yeterli bellek yok; kullanılabilir bellek bozulmuş; ya da geçersiz bir engel var., çağıran işlemin düzgün ayrılmamış olduğunu gösterir.|

Bu dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri yükler ve yeni bir işlem yürütür ve her komut satırı bağımsız değişkenini ayrı bir parametre olarak geçirir ve ortam ayarlarına bir işaretçiler dizisi geçirir.

**_Execle** işlevleri kendi parametrelerini doğrular. Varsa *■ cmdname* veya *arg0* null bir işaretçi veya boş bir dize içinde açıklanan şekilde bu işlevler geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür. Yeni bir işlem başlatılır.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**_execle**|\<Process.h >|\<errno.h >|
|**_wexecle**|\<Process.h > veya \<wchar.h >|\<errno.h >|

Daha fazla bilgi için [Uyumluluk](../../c-runtime-library/compatibility.md).

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
