---
title: _spawnve, _wspawnve | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _spawnve
- _wspawnve
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
- wspawnve
- _spawnve
- _wspawnve
- spawnve
dev_langs:
- C++
helpviewer_keywords:
- _spawnve function
- spawnve function
- wspawnve function
- processes, creating
- _wspawnve function
- processes, executing new
- process creation
ms.assetid: 26d1713d-b551-4f21-a07b-e9891a2ae6cf
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ff11a55bb9ba6a5a77255be34cb794c15e471f77
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="spawnve-wspawnve"></a>_spawnve, _wspawnve

Oluşturur ve yeni bir işlem yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*■ CmdName*<br/>
Yürütülecek dosyasının yolu.

*argv*<br/>
Bağımsız değişkenler işaretçiler dizisi. Bağımsız değişken *argv*[0] genellikle bir yol için bir işaretçi gerçek modda program adı için korumalı modda mı ve *argv*[1] aracılığıyla *argv*[**n**] için ilgili yeni bağımsız değişken listesi oluşturuluyor karakter dizeleri. Bağımsız değişken *argv*[**n** + 1] olmalıdır bir **NULL** bağımsız değişken listesinin sonuna işaretlemek için işaretçi.

*envp*<br/>
Ortam ayarları işaretçiler dizisi.

## <a name="return-value"></a>Dönüş Değeri

Bir zaman uyumlu yönteminden döndürülen değer **_spawnve** veya **_wspawnve** (**_p_waıt** için belirtilen *modu*) yeni işlemin çıkış durumu . Dönüş değerini zaman uyumsuz bir **_spawnve** veya **_wspawnve** (**_p_nowaıt** veya **_p_nowaıto** için belirtilen  *mod*) işlem tanıtıcısı. Çıkış durumu 0 ise işlemi normal şekilde sonlandırıldı. Oluşturulan işlemi özellikle çağırırsa, çıkış durumu sıfır olmayan bir değere ayarlayabilirsiniz **çıkmak** sıfır olmayan bir bağımsız değişkeni ile rutin. Yeni işlem pozitif Çıkış durumu açıkça ayarlamadıysanız pozitif Çıkış durumu bir durdurma veya bir kesme normal olmayan bir çıkış gösterir. Dönüş değeri-1 (yeni işlem başlatılmamış) bir hata gösterir. Bu durumda, **errno** aşağıdaki değerlerden birine ayarlayın.

|||
|-|-|
**E2BIG**|Bağımsız değişken listesi 1024 baytı aşıyor.
**EINVAL**|*mod* bağımsız değişkeni geçersiz.
**ENOENT**|Dosya veya yol bulunamadı.
**ENOEXEC**|Belirtilen dosya yürütülebilir değil veya yürütülebilir dosya biçimi geçersiz.
**ENOMEM**|Yeni işlemi yürütmek yeterli bellek yok.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri oluşturur ve komut satırı bağımsız değişkenleri ve ortam ayarları işaretçiler bir dizi bir dizi işaretçileri geçirme, yeni bir işlem yürütür.

Bu işlevler kendi parametreleri doğrulayın. Her iki *■ cmdname* veya *argv* null işaretçinin veya *argv* işaret null işaretçi veya *argv*[0] boş bir dize geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL**ve -1 döndürür. Yeni bir işlem oluşturdu.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_spawnve**|\<stdio.h > veya \<process.h >|
|**_wspawnve**|\<stdio.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örnekte bkz [_spawn, _wspawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
