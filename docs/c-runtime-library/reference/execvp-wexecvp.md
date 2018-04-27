---
title: _execvp, _wexecvp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _execvp function
- _wexecvp function
- wexecvp function
- execvp function
ms.assetid: a4db15df-b204-4987-be7c-de84c3414380
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 952f98e508d0814ee7f4e45f80d242777944382d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="execvp-wexecvp"></a>_execvp, _wexecvp

Yükler ve yeni alt işlemleri yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Yürütülecek dosyasının yolu.

*argv*<br/>
Parametreleri işaretçiler dizisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevler için arama işlemi döndürmeyin. Dönüş değeri-1, bu durumda bir hata gösterir **errno** genel değişkeni ayarlanır.

|**errno** değeri|Açıklama|
|-------------------|-----------------|
|**E2BIG**|Ortam ayarları ve bağımsız değişkenler için gereken alanı 32 KB'yi aşıyor.|
|**EACCES**|Belirtilen dosya kilitleme veya paylaşım ihlali var.|
|**EINVAL**|Geçersiz parametre.|
|**EMFILE**|Çok fazla dosya açık (belirtilen dosya yürütülebilir olup olmadığını belirlemek için açık olması gerekir).|
|**ENOENT**|Dosya veya yol bulunamadı.|
|**ENOEXEC**|Belirtilen dosya yürütülebilir değil veya yürütülebilir dosya biçimi geçersiz.|
|**ENOMEM**|Yeni işlemi yürütmek yeterli kullanılabilir bellek yok; kullanılabilir bellek bozulmuş; veya arama işlemi düzgün ayrılmamış olduğunu belirten bir geçersiz blok yok.|

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri yükler ve işaretçiler bir dizi komut satırı bağımsız değişkenleri geçirme ile kullanarak yeni bir işlem yürütür **yolu** yürütmek için dosyayı bulmak için ortam değişkeni.

**_Execvp** işlevleri parametrelerini doğrulayın. Varsa *■ cmdname* null işaretçinin veya *argv* null işaretçi, boş bir dizi işaretçi veya dizinin ilk bağımsız değişken olarak boş bir dize içeriyorsa, bu işlevler geçersiz parametre işleyicisi çağırma bölümünde açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür. Hiçbir işlem başlatılır.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|
|--------------|---------------------|---------------------|
|**_execvp**|\<Process.h >|\<errno.h >|
|**_wexecvp**|\<Process.h > veya \<wchar.h >|\<errno.h >|

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
