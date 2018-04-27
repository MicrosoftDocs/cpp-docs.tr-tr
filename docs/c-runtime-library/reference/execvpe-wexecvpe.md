---
title: _execvpe, _wexecvpe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _execvpe
- _wexecvpe
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
- wexecvpe
- execvpe
- _wexecvpe
- _execvpe
dev_langs:
- C++
helpviewer_keywords:
- wexecvpe function
- execvpe function
- _wexecvpe function
- _execvpe function
ms.assetid: c0c3c986-d9c0-4814-a96c-10f0b3092766
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 808f991fdf3ef8c8739eb148120922e95ec8f35a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="execvpe-wexecvpe"></a>_execvpe, _wexecvpe

Yükler ve yeni alt işlemleri çalıştırır.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*■ CmdName*<br/>
Yürütülecek dosyasının yolu.

*argv*<br/>
Parametreleri işaretçiler dizisi.

*envp*<br/>
Ortam ayarları işaretçiler dizisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevler için arama işlemi döndürmeyin. Dönüş değeri-1, bu durumda bir hata gösterir **errno** genel değişkeni ayarlanır.

|**errno** değeri|Açıklama|
|-------------------|-----------------|
|**E2BIG**|Ortam ayarları ve bağımsız değişkenler için gerekli alanı 32 KB'yi aşıyor.|
|**EACCES**|Belirtilen dosya kilitleme veya paylaşım ihlali var.|
|**EMFILE**|Çok fazla dosya açık durumda. (Belirtilen dosya yürütülebilir olup olmadığını belirlemek için açık olması gerekir.)|
|**ENOENT**|Dosya veya yol bulunamadı.|
|**ENOEXEC**|Belirtilen dosya yürütülebilir değil veya yürütülebilir dosya biçimi geçersiz.|
|**ENOMEM**|Yeni işlemi yürütmek yeterli kullanılabilir bellek yok; kullanılabilir bellek bozulmuş; veya geçersiz bir blok var, arama işlemi düzgün ayrılmamış olduğunu gösterir.|

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri yükler ve yeni bir işlem yürütür ve komut satırı bağımsız değişkenleri ve ortam ayarları işaretçiler bir dizi bir dizi işaretçileri geçirir. Bu işlevleri kullanma **yolu** yürütmek için dosyayı bulmak için ortam değişkeni.

**_Execvpe** işlevleri parametrelerini doğrulayın. Varsa *■ cmdname* null işaretçinin veya *argv* null işaretçi, boş bir dizi için bir işaretçi veya ilk bağımsız değişken olarak boş bir dize içeren bir dizi gösteren bir işaretçi, geçersiz bu işlevleri çağırma bölümünde açıklandığı gibi parametre işleyicisi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür. Hiçbir işlem başlatılır.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|
|--------------|---------------------|---------------------|
|**_execvpe**|\<Process.h >|\<errno.h >|
|**_wexecvpe**|\<Process.h > veya \<wchar.h >|\<errno.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örnekte bkz [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
