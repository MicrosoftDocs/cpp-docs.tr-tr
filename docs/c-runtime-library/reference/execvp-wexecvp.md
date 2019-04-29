---
title: _execvp, _wexecvp
ms.date: 11/04/2016
apiname:
- _execvp
- _wexecvp
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
- _execvp
- wexecvp
- _wexecvp
helpviewer_keywords:
- _execvp function
- _wexecvp function
- wexecvp function
- execvp function
ms.assetid: a4db15df-b204-4987-be7c-de84c3414380
ms.openlocfilehash: 876ace62ac46b80d42f3ed0a3549757839e0b47a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339110"
---
# <a name="execvp-wexecvp"></a>_execvp, _wexecvp

Yükler ve yeni alt işlemleri yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _execvp(
   const char *cmdname,
   const char *const *argv
);
intptr_t _wexecvp(
   const wchar_t *cmdname,
   const wchar_t *const *argv
);
```

### <a name="parameters"></a>Parametreler

*■ CmdName*<br/>
Yürütülecek dosyanın yolu.

*argv*<br/>
Parametreler için işaretçiler dizisi.

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

Bu işlevlerin her biri yükler ve komut satırı bağımsız değişkenlerine bir işaretçiler dizisi geçirerek ve kullanarak yeni bir işlem yürütür **yolu** yürütülecek dosyayı bulmak için ortam değişkeni.

**_Execvp** işlevleri kendi parametrelerini doğrular. Varsa *■ cmdname* null bir işaretçiyse veya *argv* bir bir null işaretçisiyse, işaretçe boş diziyse ya da dizinin ilk bağımsız değişken olarak boş bir dize içeriyorsa, bu işlevler geçersiz parametre işleyicisini çağırır. bölümünde anlatıldığı gibi [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür. Hiçbir işlem başlatılmadı.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**_execvp**|\<Process.h >|\<errno.h >|
|**_wexecvp**|\<Process.h > veya \<wchar.h >|\<errno.h >|

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
