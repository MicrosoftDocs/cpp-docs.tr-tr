---
title: _execl, _wexecl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _execl
- _wexecl
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
- _execl
- _wexecl
- wexecl
dev_langs:
- C++
helpviewer_keywords:
- _execl function
- wexecl function
- _wexecl function
- execl function
ms.assetid: 81fefb8a-0a06-4221-b2bc-be18e38e89f4
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 234a4f1b495c6cbfbcb047af58b6eec0f579ea61
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="execl-wexecl"></a>_execl, _wexecl

Yükler ve yeni alt işlemleri yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _execl(
   const char *cmdname,
   const char *arg0,
   ... const char *argn,
   NULL
);
intptr_t _wexecl(
   const wchar_t *cmdname,
   const wchar_t *arg0,
   ... const wchar_t *argn,
   NULL
);
```

### <a name="parameters"></a>Parametreler

*■ CmdName*<br/>
Yürütülecek dosyasının yolu.

*arg0*,... *argn*<br/>
Parametreleri işaretçiler listesi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevler için arama işlemi döndürmeyin. Dönüş değeri-1, bu durumda bir hata gösterir **errno** genel değişkeni ayarlanır.

|errno değeri|Açıklama|
|-----------------|-----------------|
|**E2BIG**|Ortam ayarları ve bağımsız değişkenler için gereken alanı 32 KB'yi aşıyor.|
|**EACCES**|Belirtilen dosya kilitleme veya paylaşım ihlali var.|
|**EINVAL**|Geçersiz parametre (bir veya daha fazla parametre olduğu bir null işaretçinin veya boş dize).|
|**EMFILE**|Çok fazla dosya açık (belirtilen dosya yürütülebilir olup olmadığını belirlemek için açık olması gerekir).|
|**ENOENT**|Dosya veya yol bulunamadı.|
|**ENOEXEC**|Belirtilen dosya yürütülebilir değil veya yürütülebilir dosya biçimi geçersiz.|
|**ENOMEM**|Yeni işlemi yürütmek yeterli kullanılabilir bellek yok; kullanılabilir bellek bozulmuş; veya arama işlemi düzgün ayrılmamış olduğunu belirten bir geçersiz blok yok.|

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri yükler ve ayrı bir parametre olarak her komut satırı bağımsız değişken geçirme, yeni bir işlem yürütür. İlk bağımsız değişken, komut veya yürütülebilir dosya adı ve ikinci bağımsız değişkeni, ilk olarak aynı olmalıdır. Bu duruma `argv[0]` yürütülen işleminde. Üçüncü bağımsız değişkeni ilk bağımsız değişkeni olan `argv[1]`, yürütülmekte olan işlemin.

**_Execl** işlevleri parametrelerini doğrulayın. Her iki *■ cmdname* veya *arg0* bir null işaretçinin ya da boş dize açıklandığı gibi bu işlevleri geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) , yürütme devam etmek için bu işlevler izin **errno** için **EINVAL** ve -1 döndürür. Yeni bir işlem yürütülür.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|
|--------------|---------------------|---------------------|
|**_execl**|\<Process.h >|\<errno.h >|
|**_wexecl**|\<Process.h > veya \<wchar.h >|\<errno.h >|

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
