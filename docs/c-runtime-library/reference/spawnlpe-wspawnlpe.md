---
title: _spawnlpe, _wspawnlpe
ms.date: 11/04/2016
apiname:
- _spawnlpe
- _wspawnlpe
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
- spawnlpe
- _wspawnlpe
- _spawnlpe
- wspawnlpe
helpviewer_keywords:
- _wspawnlpe function
- wspawnlpe function
- processes, creating
- spawnlpe function
- _spawnlpe function
- processes, executing new
- process creation
ms.assetid: e171ebfa-70e7-4c44-8331-2a291fc17bd6
ms.openlocfilehash: fa390c039a3d663cb79cb311667e568a6a053131
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327986"
---
# <a name="spawnlpe-wspawnlpe"></a>_spawnlpe, _wspawnlpe

Oluşturur ve yeni bir işlem yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _spawnlpe(
   int mode,
   const char *cmdname,
   const char *arg0,
   const char *arg1,
   ... const char *argn,
   NULL,
   const char *const *envp
);
intptr_t _wspawnlpe(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *arg0,
   const wchar_t *arg1,
   ... const wchar_t *argn,
   NULL,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>Parametreler

*Modu*<br/>
Çağırma işlemi için yürütme modu.

*■ CmdName*<br/>
Yürütülecek dosyanın yolu.

*arg0*, *arg1*,... *argn*<br/>
Bağımsız değişkenlere işaretçi listesi. *Arg0* bağımsız değişkeni, genellikle bir işaretçiye *■ cmdname*. Bağımsız değişkenler *arg1* aracılığıyla *argn* yeni bağımsız değişken listesini oluşturan karakter dizelerine. Aşağıdaki *argn*, olmalıdır bir **NULL** bağımsız değişken listesinin sonunu işaretlemek için işaretçi.

*envp*<br/>
Ortam ayarlarına bir işaretçiler dizisi.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri eş zamanlı **_spawnlpe** veya **_wspawnlpe** (**_p_waıt** için belirtilen *modu*) yeni çıkış durumudur işlem. Dönüş değeri eş zamanlı olmayan **_spawnlpe** veya **_wspawnlpe** (**_p_nowaıt** veya **_p_nowaıto** için belirtilen  *modu*) süreci işler. İşlem normal şekilde sonlandırıldıysa Çıkış durumu 0'dır. Üretilmiş işlem sıfır olmayan bir bağımsız değişken özellikle çağrılacak kullanıyorsa, çıkış durumunu sıfır olmayan bir değer ayarlayabilirsiniz **çıkmak** yordamı. Yeni işlem açık bir şekilde pozitif Çıkış durumu ayarlamadıysanız, bir pozitif Çıkış durumu bir durdurma veya kesme kaynaklanan anormal çıkışı gösterir. Dönüş değeri-1 (yeni işlem başlatılmamış) bir hata gösterir. Bu durumda, **errno** aşağıdaki değerlerden birine ayarlayın.

|||
|-|-|
| **E2BIG** | Bağımsız değişken listesi 1024 baytı aşıyor. |
| **EINVAL** | *modu* bağımsız değişkeni geçersiz. |
| **ENOENT** | Dosya veya yol bulunamadı. |
| **ENOEXEC** | Belirtilen dosya yürütülebilir değil veya geçersiz yürütülebilir dosya biçimine sahip. |
| **ENOMEM** | Yeni işlemi yürütmek yeterli bellek yok. |

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri oluşturur ve yeni bir işlem yürütür, her komut satırı bağımsız değişkenini ayrı bir parametre olarak geçirir ve ortam ayarlarına bir işaretçiler dizisi geçirir. Bu işlevleri **yolu** yürütülecek dosyayı bulmak için ortam değişkeni.

Bu işlevler kendi parametrelerini doğrular. Ya da *■ cmdname* veya *arg0* boş bir dize ya da açıklandığı şekilde bir null işaretçiyse, geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL**ve -1 döndürür. Yeni bir işlem üretilmedi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_spawnlpe**|\<Process.h >|
|**_wspawnlpe**|\<stdio.h > veya \<wchar.h >|

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
