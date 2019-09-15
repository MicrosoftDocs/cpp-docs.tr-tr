---
title: _execvpe, _wexecvpe
ms.date: 11/04/2016
api_name:
- _execvpe
- _wexecvpe
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
- wexecvpe
- execvpe
- _wexecvpe
- _execvpe
helpviewer_keywords:
- wexecvpe function
- execvpe function
- _wexecvpe function
- _execvpe function
ms.assetid: c0c3c986-d9c0-4814-a96c-10f0b3092766
ms.openlocfilehash: eab63cd54d410daf1dd4d09fb3d904feca0a230d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941734"
---
# <a name="_execvpe-_wexecvpe"></a>_execvpe, _wexecvpe

Yeni alt süreçler yükler ve çalıştırır.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _execvpe(
   const char *cmdname,
   const char *const *argv,
   const char *const *envp
);
intptr_t _wexecvpe(
   const wchar_t *cmdname,
   const wchar_t *const *argv,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>Parametreler

*cmdname*<br/>
Yürütülecek dosyanın yolu.

*argv*<br/>
Parametrelere işaretçiler dizisi.

*envp*<br/>
Ortam ayarlarına işaretçiler dizisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevler çağıran işleme geri dönmez. -1 ' in dönüş değeri bir hatayı gösterir, bu durumda **errno** genel değişkeni ayarlanır.

|**errno** değeri|Açıklama|
|-------------------|-----------------|
|**E2BIG**|Bağımsız değişkenler ve ortam ayarları için gereken alan 32 KB 'yi aşıyor.|
|**EACCES**|Belirtilen dosyada bir kilitleme veya paylaşım ihlali vardır.|
|**EMFILE**|Çok fazla dosya açık. (Çalıştırılabilir olup olmadığını anlamak için belirtilen dosyanın açılması gerekir.)|
|**ENOENT**|Dosya veya yol bulunamadı.|
|**ENOEXEC**|Belirtilen dosya yürütülebilir değil veya geçersiz bir yürütülebilir dosya biçimine sahip.|
|**ENOMEM**|Yeni işlemi yürütmek için yeterli kullanılabilir bellek yok; kullanılabilir bellek bozulmuş; ya da çağıran işlemin doğru şekilde ayrılmadığını gösteren geçersiz bir blok var.|

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri yeni bir işlem yükler ve yürütür ve komut satırı bağımsız değişkenlerine bir işaretçiler dizisi ve ortam ayarlarına işaretçiler dizisi geçirir. Bu işlevler, yürütülecek dosyayı bulmak için **Path** ortam değişkenini kullanır.

**_Execvpe** işlevleri parametrelerini doğrular. *Cmdname* null bir işaretçiyse veya *argv* boş bir işaretçi, boş bir diziye yönelik bir işaretçi veya ilk bağımsız değişken olarak boş bir dize içeren bir dizi işaretçisi ise, bu işlevler, içinde [açıklandığı gibi geçersiz parametre işleyicisini çağırır. Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve-1 döndürür. Hiçbir işlem başlatılmadı.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**_execvpe**|\<Process. h >|\<errno. h >|
|**_wexecvpe**|\<Process. h > veya \<wchar. h >|\<errno. h >|

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
