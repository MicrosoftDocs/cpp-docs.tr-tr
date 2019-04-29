---
title: _execl, _wexecl
ms.date: 11/04/2016
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
helpviewer_keywords:
- _execl function
- wexecl function
- _wexecl function
- execl function
ms.assetid: 81fefb8a-0a06-4221-b2bc-be18e38e89f4
ms.openlocfilehash: 3d736849f90782425e6e1c1cff04536972318c91
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339279"
---
# <a name="execl-wexecl"></a>_execl, _wexecl

Yükler ve yeni alt işlemleri yürütür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Yürütülecek dosyanın yolu.

*arg0*,... *argn*<br/>
Parametreler için işaretçiler listesi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevler çağırma işlemine geri gitmez. -1 değeri, bu durumda bir hata belirtir **errno** global değişkeni ayarlanır.

|errno değeri|Açıklama|
|-----------------|-----------------|
|**E2BIG**|Bağımsız değişkenler ve ortam ayarları için gereken alan 32 KB aşıyor.|
|**SPAWN**|Belirtilen dosya kilitleme veya paylaşma ihlali var.|
|**EINVAL**|Geçersiz parametre (bir veya daha fazla parametre bir null işaretçi veya boş dizeydi).|
|**EMFILE**|Çok fazla dosya açık (belirtilen dosyanın yürütülebilir olup olmadığını belirlemek için açılması gerekir).|
|**ENOENT**|Dosya veya yol bulunamadı.|
|**ENOEXEC**|Belirtilen dosya yürütülebilir değil veya geçersiz bir yürütülebilir dosya biçimine sahip.|
|**ENOMEM**|Yeni işlemi yürütmek yeterli bellek yok; kullanılabilir bellek bozulmuş; veya, çağırma işlemi düzgün ayrılmamış olduğunu belirten geçersiz bir engel var.|

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, yükler ve her komut satırı bağımsız değişkenini ayrı bir parametre geçirerek yeni bir işlem yürütür. İlk bağımsız değişken komut veya yürütülebilir dosya adıdır ve ikinci bağımsız değişken Birincisi ile aynı olmalıdır. Bu duruma `argv[0]` yürütülen işlemde. Üçüncü bağımsız değişkeni olmayan ilk bağımsız değişken `argv[1]`, yürütülmekte olan işlemin.

**_Execl** işlevleri kendi parametrelerini doğrular. Ya da *■ cmdname* veya *arg0* bir null işaretçi veya boş bir dize içinde açıklanan şekilde bu işlevler geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md) , yürütme devam etmek için bu işlevler izin **errno** için **EINVAL** ve -1 döndürür. Yeni bir işlem yürütülmedi.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**_execl**|\<Process.h >|\<errno.h >|
|**_wexecl**|\<Process.h > veya \<wchar.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örnekte bakın [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
