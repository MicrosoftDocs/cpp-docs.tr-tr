---
title: _spawnv, _wspawnv | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wspawnv
- _spawnv
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
- wspawnv
- _spawnv
- _wspawnv
dev_langs:
- C++
helpviewer_keywords:
- wspawnv function
- processes, creating
- _spawnv function
- processes, executing new
- process creation
- _wspawnv function
- spawnv function
ms.assetid: 72360ef4-dfa9-44c1-88c1-b3ecb660aa7d
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 30e55677395f528b15de90ba2045bb7e0785ca9a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="spawnv-wspawnv"></a>_spawnv, _wspawnv

Oluşturur ve yeni bir işlem yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _spawnv(
   int mode,
   const char *cmdname,
   const char *const *argv
);
intptr_t _wspawnv(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv
);
```

### <a name="parameters"></a>Parametreler

*Modu*<br/>
Arama işlemi için yürütme modu.

*■ CmdName*<br/>
Yürütülecek dosyasının yolu.

*argv*<br/>
Bağımsız değişkenler işaretçiler dizisi. Bağımsız değişken *argv*[0] genellikle bir yol için bir işaretçi gerçek modda program adı için korumalı modda mı ve *argv*[1] aracılığıyla *argv*[**n**] için ilgili yeni bağımsız değişken listesi oluşturuluyor karakter dizeleri. Bağımsız değişken *argv*[**n** + 1] olmalıdır bir **NULL** bağımsız değişken listesinin sonuna işaretlemek için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bir zaman uyumlu yönteminden döndürülen değer **_spawnv** veya **_wspawnv** (**_p_waıt** için belirtilen *modu*) yeni işlem çıkış durumudur. Dönüş değerini zaman uyumsuz bir **_spawnv** veya **_wspawnv** (**_p_nowaıt** veya **_p_nowaıto** için belirtilen *modu* ) işlem tanıtıcısı. Çıkış durumu 0 ise işlemi normal şekilde sonlandırıldı. Oluşturulan işlemi özellikle çağırırsa, çıkış durumu sıfır olmayan bir değere ayarlayabilirsiniz **çıkmak** sıfır olmayan bir bağımsız değişkeni ile rutin. Yeni işlem pozitif Çıkış durumu açıkça ayarlamadıysanız pozitif Çıkış durumu bir durdurma veya bir kesme normal olmayan bir çıkış gösterir. Dönüş değeri-1 (yeni işlem başlatılmamış) bir hata gösterir. Bu durumda, **errno** aşağıdaki değerlerden birine ayarlayın.

|||
|-|-|
**E2BIG**|Bağımsız değişken listesi 1024 baytı aşıyor.
**EINVAL**|*mod* bağımsız değişkeni geçersiz.
**ENOENT**|Dosya veya yol bulunamadı.
**ENOEXEC**|Belirtilen dosya yürütülebilir değil veya yürütülebilir dosya biçimi geçersiz.
**ENOMEM**|Yeni işlemi yürütmek yeterli bellek yok.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri oluşturur ve bir dizi işaretçileri için komut satırı bağımsız değişkenleri geçirme, yeni bir işlem yürütür.

Bu işlevler kendi parametreleri doğrulayın. Her iki *■ cmdname* veya *argv* null işaretçinin veya *argv* işaret null işaretçi veya *argv*[0] boş bir dize geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL**ve -1 döndürür. Yeni bir işlem oluşturdu.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_spawnv**|\<stdio.h > veya \<process.h >|
|**_wspawnv**|\<stdio.h > veya \<wchar.h >|

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
