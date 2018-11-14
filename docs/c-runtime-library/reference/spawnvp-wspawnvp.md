---
title: _spawnvp, _wspawnvp
ms.date: 11/04/2016
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
helpviewer_keywords:
- wspawnvp function
- processes, creating
- _wspawnvp function
- processes, executing new
- spawnvp function
- process creation
- _spawnvp function
ms.assetid: 8d8774ec-6ad4-4680-a5aa-440cde1e0249
ms.openlocfilehash: b697eabd7a45eedbf9c892acee570a9e8b818d1b
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330729"
---
# <a name="spawnvp-wspawnvp"></a>_spawnvp, _wspawnvp

Bir işlem oluşturur ve yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Çağırma işlemi için yürütme modu.

*■ CmdName*<br/>
Yürütülecek dosyanın yolu.

*argv*<br/>
İşaretçiler bağımsız değişkenler dizisi. Bağımsız değişken *argv*[0] genellikle bir yol için bir işaretçi gerçek modda program adına korumalı modda mı ve *argv*[1] aracılığıyla *argv*[**n**] yeni bağımsız değişken listesini oluşturan karakter dizelerine. Bağımsız değişken *argv*[**n** + 1] olmalıdır bir **NULL** bağımsız değişken listesinin sonunu işaretlemek için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri eş zamanlı **_spawnvp** veya **_wspawnvp** (**_p_waıt** için belirtilen *modu*) yeni sürecin çıkış durumudur . Dönüş değeri eş zamanlı olmayan **_spawnvp** veya **_wspawnvp** (**_p_nowaıt** veya **_p_nowaıto** için belirtilen  *modu*) süreci işler. İşlem normal şekilde sonlandırıldıysa Çıkış durumu 0'dır. Üretilmiş işlem sıfır olmayan bir bağımsız değişken özellikle çağrılacak kullanıyorsa, çıkış durumunu sıfır olmayan bir değer ayarlayabilirsiniz **çıkmak** yordamı. Yeni işlem açık bir şekilde pozitif Çıkış durumu ayarlamadıysanız, bir pozitif Çıkış durumu bir durdurma veya kesme kesintili anormal çıkışı gösterir. Dönüş değeri-1 (yeni işlem başlatılmamış) bir hata gösterir. Bu durumda, **errno** aşağıdaki değerlerden birine ayarlayın:

|||
|-|-|
| **E2BIG** | Bağımsız değişken listesi 1024 baytı aşıyor. |
| **EINVAL** | *modu* bağımsız değişkeni geçersiz. |
| **ENOENT** | Dosya veya yol bulunamadı. |
| **ENOEXEC** | Belirtilen dosya yürütülebilir değil veya geçersiz yürütülebilir dosya biçimine sahip. |
| **ENOMEM** | Yeni işlemi yürütmek yeterli bellek yok. |

Bunlar ve diğer hakkında daha fazla bilgi, dönüş kodları, bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri yeni bir işlem oluşturur ve yürütür ve komut satırı bağımsız değişkenleri ve kullandığı bir işaretçiler dizisi geçirir **yolu** yürütülecek dosyayı bulmak için ortam değişkeni.

Bu işlevler kendi parametrelerini doğrular. Ya da *■ cmdname* veya *argv* null bir işaretçiyse veya *argv* boş işaretçiyi veya *argv*[0] boş bir dize geçersiz parametre işleyicisi çağrılır, açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL**ve -1 döndürür. Yeni bir işlem üretilmedi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_spawnvp**|\<stdio.h > veya \<process.h >|
|**_wspawnvp**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
