---
title: _spawnvpe, _wspawnvpe
ms.date: 11/04/2016
apiname:
- _spawnvpe
- _wspawnvpe
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
- _spawnvpe
- wspawnvpe
- spawnvpe
- _wspawnvpe
helpviewer_keywords:
- _wspawnvpe function
- processes, creating
- _spawnvpe function
- processes, executing new
- wspawnvpe function
- process creation
- spawnvpe function
ms.assetid: 3db6394e-a955-4837-97a1-fab1db1e6092
ms.openlocfilehash: a98cc3c441261a92876b94e1231e66bb71e9d3d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62355087"
---
# <a name="spawnvpe-wspawnvpe"></a>_spawnvpe, _wspawnvpe

Oluşturur ve yeni bir işlem yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _spawnvpe(
   int mode,
   const char *cmdname,
   const char *const *argv,
   const char *const *envp
);
intptr_t _wspawnvpe(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>Parametreler

*Modu*<br/>
Çağırma işlemi için yürütme modu

*■ CmdName*<br/>
Yürütülecek dosyanın yolu

*argv*<br/>
İşaretçiler bağımsız değişkenler dizisi. Bağımsız değişken *argv*[0] genellikle bir yol için bir işaretçi gerçek modda program adına korumalı modda mı ve *argv*[1] aracılığıyla *argv*[**n**] yeni bağımsız değişken listesini oluşturan karakter dizelerine. Bağımsız değişken *argv*[**n** + 1] olmalıdır bir **NULL** bağımsız değişken listesinin sonunu işaretlemek için işaretçi.

*envp*<br/>
Ortam ayarlarına bir işaretçiler dizisi

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri eş zamanlı **_spawnvpe** veya **_wspawnvpe** (**_p_waıt** için belirtilen *modu*) yeni çıkış durumudur işlem. Dönüş değeri eş zamanlı olmayan **_spawnvpe** veya **_wspawnvpe** (**_p_nowaıt** veya **_p_nowaıto** için belirtilen  *modu*) süreci işler. İşlem normal şekilde sonlandırıldıysa Çıkış durumu 0'dır. Üretilmiş işlem özellikle çağırırsa, çıkış durumu sıfır olmayan bir değer ayarlayabilirsiniz **çıkmak** rutin sıfır olmayan bir bağımsız değişken. Yeni işlem açık bir şekilde pozitif Çıkış durumu ayarlamadıysanız, bir pozitif Çıkış durumu bir durdurma veya kesme kesintili anormal çıkışı gösterir. Dönüş değeri-1 (yeni işlem başlatılmamış) bir hata gösterir. Bu durumda, **errno** aşağıdaki değerlerden birine ayarlayın:

|||
|-|-|
| **E2BIG** | Bağımsız değişken listesi 1024 baytı aşıyor. |
| **EINVAL** | *modu* bağımsız değişkeni geçersiz. |
| **ENOENT** | Dosya veya yol bulunamadı. |
| **ENOEXEC** | Belirtilen dosya yürütülebilir değil veya geçersiz yürütülebilir dosya biçimine sahip. |
| **ENOMEM** | Yeni işlemi yürütmek yeterli bellek yok. |

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, oluşturur ve bir işaretçiler dizisi komut satırı bağımsız değişkenleri ve bir ortam ayarlarına bir işaretçiler dizisi geçirerek yeni bir işlem yürütür. Bu işlevleri **yolu** yürütülecek dosyayı bulmak için ortam değişkeni.

Bu işlevler kendi parametrelerini doğrular. Ya da *■ cmdname* veya *argv* null bir işaretçiyse veya *argv* boş işaretçiyi veya *argv*[0] boş bir dize geçersiz parametre işleyicisi çağrılır, açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL**ve -1 döndürür. Yeni bir işlem üretilmedi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_spawnvpe**|\<stdio.h > veya \<process.h >|
|**_wspawnvpe**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örnekte bakın [_spawn, _wspawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md).

## <a name="see-also"></a>Ayrıca bkz.

[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
