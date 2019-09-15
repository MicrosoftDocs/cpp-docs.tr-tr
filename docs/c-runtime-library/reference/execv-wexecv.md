---
title: _execv, _wexecv
ms.date: 11/04/2016
api_name:
- _wexecv
- _execv
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
- _execv
- _wexecv
- wexecv
helpviewer_keywords:
- _wexecv function
- _execv function
- wexecv function
- execv function
ms.assetid: 8dbaf7bc-9040-4316-a0c1-db7e866b52af
ms.openlocfilehash: bb18603c618342f67bad28ebf0b99bd173ee5293
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941849"
---
# <a name="_execv-_wexecv"></a>_execv, _wexecv

Yeni alt süreçler yükler ve yürütür.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*cmdname*<br/>
Yürütülecek dosyanın yolu.

*argv*<br/>
Parametrelere işaretçiler dizisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevler çağıran işleme geri dönmez. -1 ' in dönüş değeri bir hatayı gösterir, bu durumda **errno** genel değişkeni ayarlanır.

|**errno** değeri|Açıklama|
|-------------------|-----------------|
|**E2BIG**|Bağımsız değişkenler ve ortam ayarları için gereken alan 32 KB 'yi aşıyor.|
|**EACCES**|Belirtilen dosyada bir kilitleme veya paylaşım ihlali vardır.|
|**EINVAL**|Geçersiz parametre.|
|**EMFILE**|Çok fazla dosya açık (belirtilen dosyanın yürütülebilir olup olmadığını anlamak için açılması gerekir).|
|**ENOENT**|Dosya veya yol bulunamadı.|
|**ENOEXEC**|Belirtilen dosya yürütülebilir değil veya geçersiz bir yürütülebilir dosya biçimine sahip.|
|**ENOMEM**|Yeni işlemi yürütmek için yeterli kullanılabilir bellek yok; kullanılabilir bellek bozulmuş; ya da çağıran işlemin düzgün bir şekilde ayrılmadığını belirten geçersiz bir blok var.|

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, komut satırı bağımsız değişkenlerine işaretçiler dizisi geçirerek yeni bir işlem yükler ve yürütür.

**_Execv** işlevleri parametrelerini doğrular. *Cmdname* null bir işaretçiyse veya *argv* null işaretçisiyse, boş bir dizi işaretçisiyse veya dizi ilk bağımsız değişken olarak boş bir dize içeriyorsa, **_execv** işlevleri parametre bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır [ Doğrulama](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve-1 döndürür. Hiçbir işlem başlatılmadı.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**_execv**|\<Process. h >|\<errno. h >|
|**_wexecv**|\<Process. h > veya \<wchar. h >|\<errno. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Exec, _wexec Functions](../../c-runtime-library/exec-wexec-functions.md)içindeki örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
