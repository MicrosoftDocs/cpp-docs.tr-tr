---
title: _spawnv, _wspawnv
ms.date: 11/04/2016
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
helpviewer_keywords:
- wspawnv function
- processes, creating
- _spawnv function
- processes, executing new
- process creation
- _wspawnv function
- spawnv function
ms.assetid: 72360ef4-dfa9-44c1-88c1-b3ecb660aa7d
ms.openlocfilehash: 4f6e24135a040e0b081016041192d2ae196d1037
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50576756"
---
# <a name="spawnv-wspawnv"></a>_spawnv, _wspawnv

Oluşturur ve yeni bir işlem yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Çağırma işlemi için yürütme modu.

*■ CmdName*<br/>
Yürütülecek dosyanın yolu.

*argv*<br/>
İşaretçiler bağımsız değişkenler dizisi. Bağımsız değişken *argv*[0] genellikle bir yol için bir işaretçi gerçek modda program adına korumalı modda mı ve *argv*[1] aracılığıyla *argv*[**n**] yeni bağımsız değişken listesini oluşturan karakter dizelerine. Bağımsız değişken *argv*[**n** + 1] olmalıdır bir **NULL** bağımsız değişken listesinin sonunu işaretlemek için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri eş zamanlı **_spawnv** veya **_wspawnv** (**_p_waıt** için belirtilen *modu*) yeni sürecin çıkış durumudur. Dönüş değeri eş zamanlı olmayan **_spawnv** veya **_wspawnv** (**_p_nowaıt** veya **_p_nowaıto** için belirtilen *modu* ) süreci işler. İşlem normal şekilde sonlandırıldıysa Çıkış durumu 0'dır. Üretilmiş işlem özellikle çağırırsa, çıkış durumu sıfır olmayan bir değer ayarlayabilirsiniz **çıkmak** rutin sıfır olmayan bir bağımsız değişken. Yeni işlem açık bir şekilde pozitif Çıkış durumu ayarlamadıysanız, bir pozitif Çıkış durumu bir durdurma veya kesme kesintili anormal çıkışı gösterir. Dönüş değeri-1 (yeni işlem başlatılmamış) bir hata gösterir. Bu durumda, **errno** aşağıdaki değerlerden birine ayarlayın.

|||
|-|-|
**E2BIG**|Bağımsız değişken listesi 1024 baytı aşıyor.
**EINVAL**|*modu* bağımsız değişkeni geçersiz.
**ENOENT**|Dosya veya yol bulunamadı.
**ENOEXEC**|Belirtilen dosya yürütülebilir değil veya geçersiz yürütülebilir dosya biçimine sahip.
**ENOMEM**|Yeni işlemi yürütmek yeterli bellek yok.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, oluşturur ve komut satırı bağımsız değişkenlerine bir işaretçiler dizisi geçirerek yeni bir işlem yürütür.

Bu işlevler kendi parametrelerini doğrular. Ya da *■ cmdname* veya *argv* null bir işaretçiyse veya *argv* boş işaretçiyi veya *argv*[0] boş bir dize geçersiz parametre işleyicisi çağrılır, açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL**ve -1 döndürür. Yeni bir işlem üretilmedi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_spawnv**|\<stdio.h > veya \<process.h >|
|**_wspawnv**|\<stdio.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örnekte bakın [_spawn, _wspawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md).

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
