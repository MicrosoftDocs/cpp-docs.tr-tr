---
title: _spawnvp, _wspawnvp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wspawnvp
- _spawnvp
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
- _wspawnvp
- _spawnvp
- wspawnvp
dev_langs:
- C++
helpviewer_keywords:
- wspawnvp function
- processes, creating
- _wspawnvp function
- processes, executing new
- spawnvp function
- process creation
- _spawnvp function
ms.assetid: 8d8774ec-6ad4-4680-a5aa-440cde1e0249
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e31cb0d21b6ac626dcf00c6a80e50b924adac285
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="spawnvp-wspawnvp"></a>_spawnvp, _wspawnvp

Bir işlem oluşturur ve yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _spawnvp(
   int mode,
   const char *cmdname,
   const char *const *argv
);
intptr_t _wspawnvp(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv
);
```

### <a name="parameters"></a>Parametreler

*Modu*<br/>
İşlem çağırmak için yürütme modu.

*■ CmdName*<br/>
Yürütülecek dosyasının yolu.

*argv*<br/>
Bağımsız değişkenler işaretçiler dizisi. Bağımsız değişken *argv*[0] genellikle bir yol için bir işaretçi gerçek modda program adı için korumalı modda mı ve *argv*[1] aracılığıyla *argv*[**n**] için ilgili yeni bağımsız değişken listesi form karakter dizeleri. Bağımsız değişken *argv*[**n** + 1] olmalıdır bir **NULL** bağımsız değişken listesinin sonuna işaretlemek için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bir zaman uyumlu yönteminden döndürülen değer **_spawnvp** veya **_wspawnvp** (**_p_waıt** için belirtilen *modu*) yeni işlemin çıkış durumu . Dönüş değerini zaman uyumsuz bir **_spawnvp** veya **_wspawnvp** (**_p_nowaıt** veya **_p_nowaıto** için belirtilen  *mod*) işlem tanıtıcısı. Çıkış durumu 0 ise işlemi normal şekilde sonlandırıldı. Oluşturulan işlemi çağırmak için sıfır olmayan bir bağımsız değişken özellikle kullanıyorsa, çıkış durumu sıfır olmayan bir değere ayarlayabilirsiniz **çıkmak** yordamı. Yeni işlem pozitif Çıkış durumu açıkça ayarlamadıysanız pozitif Çıkış durumu bir durdurma veya bir kesme normal olmayan bir çıkış gösterir. Dönüş değeri-1 (yeni işlem başlatılmamış) bir hata gösterir. Bu durumda, **errno** aşağıdaki değerlerden birine ayarlayın:

|||
|-|-|
**E2BIG**|Bağımsız değişken listesi 1024 baytı aşıyor.
**EINVAL**|*mod* bağımsız değişkeni geçersiz.
**ENOENT**|Dosya veya yol bulunamadı.
**ENOEXEC**|Belirtilen dosya yürütülebilir değil veya yürütülebilir dosya biçimi geçersiz.
**ENOMEM**|Yeni işlemi yürütmek yeterli bellek yok.

Bu ve diğer hakkında daha fazla bilgi için dönüş kodları, bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri yeni bir işlem oluşturur ve yürütür ve komut satırı bağımsız değişkenleri ve kullandığı bir dizi işaretçileri geçirir **yolu** yürütmek için dosyayı bulmak için ortam değişkeni.

Bu işlevler kendi parametreleri doğrulayın. Her iki *■ cmdname* veya *argv* null işaretçinin veya *argv* işaret null işaretçi veya *argv*[0] boş bir dize geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL**ve -1 döndürür. Yeni bir işlem oluşturdu.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_spawnvp**|\<stdio.h > veya \<process.h >|
|**_wspawnvp**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
