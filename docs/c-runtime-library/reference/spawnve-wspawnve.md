---
title: _spawnve, _wspawnve
ms.date: 11/04/2016
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
helpviewer_keywords:
- _spawnve function
- spawnve function
- wspawnve function
- processes, creating
- _wspawnve function
- processes, executing new
- process creation
ms.assetid: 26d1713d-b551-4f21-a07b-e9891a2ae6cf
ms.openlocfilehash: 3e3a8d3cf476dfff7c74007ec371c39f5128bbe7
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326484"
---
# <a name="spawnve-wspawnve"></a>_spawnve, _wspawnve

Oluşturur ve yeni bir işlem yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Çağırma işlemi için yürütme modu.

*■ CmdName*<br/>
Yürütülecek dosyanın yolu.

*argv*<br/>
İşaretçiler bağımsız değişkenler dizisi. Bağımsız değişken *argv*[0] genellikle bir yol için bir işaretçi gerçek modda program adına korumalı modda mı ve *argv*[1] aracılığıyla *argv*[**n**] yeni bağımsız değişken listesini oluşturan karakter dizelerine. Bağımsız değişken *argv*[**n** + 1] olmalıdır bir **NULL** bağımsız değişken listesinin sonunu işaretlemek için işaretçi.

*envp*<br/>
Ortam ayarlarına bir işaretçiler dizisi.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri eş zamanlı **_spawnve** veya **_wspawnve** (**_p_waıt** için belirtilen *modu*) yeni sürecin çıkış durumudur . Dönüş değeri eş zamanlı olmayan **_spawnve** veya **_wspawnve** (**_p_nowaıt** veya **_p_nowaıto** için belirtilen  *modu*) süreci işler. İşlem normal şekilde sonlandırıldıysa Çıkış durumu 0'dır. Üretilmiş işlem özellikle çağırırsa, çıkış durumu sıfır olmayan bir değer ayarlayabilirsiniz **çıkmak** rutin sıfır olmayan bir bağımsız değişken. Yeni işlem açık bir şekilde pozitif Çıkış durumu ayarlamadıysanız, bir pozitif Çıkış durumu bir durdurma veya kesme kesintili anormal çıkışı gösterir. Dönüş değeri-1 (yeni işlem başlatılmamış) bir hata gösterir. Bu durumda, **errno** aşağıdaki değerlerden birine ayarlayın.

|||
|-|-|
| **E2BIG** | Bağımsız değişken listesi 1024 baytı aşıyor. |
| **EINVAL** | *modu* bağımsız değişkeni geçersiz. |
| **ENOENT** | Dosya veya yol bulunamadı. |
| **ENOEXEC** | Belirtilen dosya yürütülebilir değil veya geçersiz yürütülebilir dosya biçimine sahip. |
| **ENOMEM** | Yeni işlemi yürütmek yeterli bellek yok. |

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, oluşturur ve bir işaretçiler dizisi komut satırı bağımsız değişkenleri ve bir ortam ayarlarına bir işaretçiler dizisi geçirerek yeni bir işlem yürütür.

Bu işlevler kendi parametrelerini doğrular. Ya da *■ cmdname* veya *argv* null bir işaretçiyse veya *argv* boş işaretçiyi veya *argv*[0] boş bir dize geçersiz parametre işleyicisi çağrılır, açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL**ve -1 döndürür. Yeni bir işlem üretilmedi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_spawnve**|\<stdio.h > veya \<process.h >|
|**_wspawnve**|\<stdio.h > veya \<wchar.h >|

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
