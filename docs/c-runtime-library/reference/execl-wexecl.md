---
title: _execl, _wexecl
ms.date: 11/04/2016
api_name:
- _execl
- _wexecl
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 714ef80c4909e92100c4fa869b7544239f8edeb7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941947"
---
# <a name="_execl-_wexecl"></a>_execl, _wexecl

Yeni alt süreçler yükler ve yürütür.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*cmdname*<br/>
Yürütülecek dosyanın yolu.

*arg0*,... *argN*<br/>
Parametrelerin işaretçilerin listesi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevler çağıran işleme geri dönmez. -1 ' in dönüş değeri bir hatayı gösterir, bu durumda **errno** genel değişkeni ayarlanır.

|errno değeri|Açıklama|
|-----------------|-----------------|
|**E2BIG**|Bağımsız değişkenler ve ortam ayarları için gereken alan 32 KB 'yi aşıyor.|
|**EACCES**|Belirtilen dosyada bir kilitleme veya paylaşım ihlali vardır.|
|**EINVAL**|Geçersiz parametre (bir veya daha fazla parametre null işaretçi veya boş dize).|
|**EMFILE**|Çok fazla dosya açık (belirtilen dosyanın yürütülebilir olup olmadığını anlamak için açılması gerekir).|
|**ENOENT**|Dosya veya yol bulunamadı.|
|**ENOEXEC**|Belirtilen dosya yürütülebilir değil veya geçersiz bir yürütülebilir dosya biçimine sahip.|
|**ENOMEM**|Yeni işlemi yürütmek için yeterli kullanılabilir bellek yok; kullanılabilir bellek bozulmuş; ya da çağıran işlemin düzgün bir şekilde ayrılmadığını belirten geçersiz bir blok var.|

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, her komut satırı bağımsız değişkenini ayrı bir parametre olarak geçirerek yeni bir işlem yükler ve yürütür. İlk bağımsız değişken komut veya yürütülebilir dosya adıdır ve ikinci bağımsız değişken ilki ile aynı olmalıdır. Yürütülen işlemde `argv[0]` olur. Üçüncü bağımsız değişken, yürütülen işlemin ilk bağımsız `argv[1]`değişkenidir.

**_Execl** işlevleri parametrelerini doğrular. Herhangi bir *cmdname* veya *arg0* null işaretçi ya da boş dize ise, yürütmenin devam etmesine izin veriliyorsa, bu işlevler geçersiz parametre [](../../c-runtime-library/parameter-validation.md) işleyicisini çağırır, bu işlevler **errno** **olarak ayarlanır. EıNVAL** ve Return-1. Yeni bir işlem yürütülmedi.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**_execl**|\<Process. h >|\<errno. h >|
|**_wexecl**|\<Process. h > veya \<wchar. h >|\<errno. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Exec, _wexec Functions](../../c-runtime-library/exec-wexec-functions.md)içindeki örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
