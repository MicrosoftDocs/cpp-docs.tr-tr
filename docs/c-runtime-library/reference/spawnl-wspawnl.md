---
title: _spawnl, _wspawnl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wspawnl
- _spawnl
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
- spawnl
- wspawnl
- _wspawnl
- _spawnl
dev_langs:
- C++
helpviewer_keywords:
- spawnl function
- processes, creating
- _spawnl function
- processes, executing new
- _wspawnl function
- wspawnl function
- process creation
ms.assetid: dd4584c9-7173-4fc5-b93a-6e7d3c2316d7
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d87644ab30997e8f29cd59e254eef6191c4cd539
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="spawnl-wspawnl"></a>_spawnl, _wspawnl

Oluşturur ve yeni bir işlem yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _spawnl(
   int mode,
   const char *cmdname,
   const char *arg0,
   const char *arg1,
   ... const char *argn,
   NULL
);
intptr_t _wspawnl(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *arg0,
   const wchar_t *arg1,
   ... const wchar_t *argn,
   NULL
);
```

### <a name="parameters"></a>Parametreler

*Modu*<br/>
Arama işlemi için yürütme modu.

*■ CmdName*<br/>
Yürütülecek dosyasının yolu.

*arg0*, *arg1*,... *argn*<br/>
Bağımsız değişkenler işaretçiler listesi. *Arg0* bağımsız değişkeni genellikle bir işaretçidir *■ cmdname*. Bağımsız değişkenler *arg1* aracılığıyla *argn* yeni bağımsız değişken listesi oluşturuluyor karakter dizelerini işaretçileridir. Aşağıdaki *argn*, olmalıdır bir **NULL** bağımsız değişken listesinin sonuna işaretlemek için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bir zaman uyumlu yönteminden döndürülen değer **_spawnl** veya **_wspawnl** (**_p_waıt** için belirtilen *modu*) yeni işlem çıkış durumudur. Dönüş değerini zaman uyumsuz bir **_spawnl** veya **_wspawnl** (**_p_nowaıt** veya **_p_nowaıto** için belirtilen *modu* ) işlem tanıtıcısı. Çıkış durumu 0 ise işlemi normal şekilde sonlandırıldı. Oluşturulan işlemi özellikle çağırırsa, çıkış durumu sıfır olmayan bir değere ayarlayabilirsiniz **çıkmak** sıfır olmayan bir bağımsız değişkeni ile rutin. Yeni işlem pozitif Çıkış durumu açıkça ayarlamadıysanız pozitif Çıkış durumu bir durdurma veya bir kesme normal olmayan bir çıkış gösterir. Dönüş değeri-1 (yeni işlem başlatılmamış) bir hata gösterir. Bu durumda, **errno** aşağıdaki değerlerden birine ayarlayın.

|||
|-|-|
**E2BIG**|Bağımsız değişken listesi 1024 baytı aşıyor.
**EINVAL**|*mod* bağımsız değişkeni geçersiz.
**ENOENT**|Dosya veya yol bulunamadı.
**ENOEXEC**|Belirtilen dosya yürütülebilir değil veya yürütülebilir dosya biçimi geçersiz.
**ENOMEM**|Yeni işlemi yürütmek yeterli bellek yok.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bu işlevler kendi parametreleri doğrulayın. Her iki *■ cmdname* veya *arg0* boş bir dize ya da açıklandığı gibi geçersiz parametre işleyicisi null işaretçi çağrılan [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL**ve -1 döndürür. Yeni bir işlem oluşturdu.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri oluşturur ve ayrı bir parametre olarak her komut satırı bağımsız değişken geçirme, yeni bir işlem yürütür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_spawnl**|\<Process.h >|
|**_wspawnl**|\<stdio.h > veya \<wchar.h >|

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
