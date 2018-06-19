---
title: _getcwd_dbg, _wgetcwd_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wgetcwd_dbg
- _getcwd_dbg
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd_dbg
- _wgetcwd_dbg
- getcwd_dbg
- wgetcwd_dbg
dev_langs:
- C++
helpviewer_keywords:
- wgetcwd_dbg function
- working directory
- _getcwd_dbg function
- getcwd_dbg function
- current working directory
- _wgetcwd_dbg function
- directories [C++], current working
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b4124b5825f27ec26afdb40f0ccc9e4de4ed087
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401561"
---
# <a name="getcwddbg-wgetcwddbg"></a>_getcwd_dbg, _wgetcwd_dbg

Hata ayıklama sürümleri [_getcwd, _wgetcwd](getcwd-wgetcwd.md) işlevleri (yalnızca hata ayıklama sırasında kullanılabilir).

## <a name="syntax"></a>Sözdizimi

```C
char *_getcwd_dbg(
   char *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wgetcwd_dbg(
   wchar_t *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Yol için depolama konumu.

*maxlen*<br/>
Yolun karakter cinsinden en büyük uzunluğu: **char** için **_getcwd_dbg** ve **wchar_t** için **_wgetcwd_dbg**.

*blockType*<br/>
İstenen bellek bloğu türü: **_clıent_block** veya **_NORMAL_BLOCK**.

*Dosya adı*<br/>
İstenen ayırma işlemi kaynak dosyasının adını işaretçi veya **NULL**.

*LineNumber*<br/>
Satır numarası ayırma işlemi istenen burada kaynak dosyasında veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

Bir işaretçi döndürür *arabellek*. A **NULL** değeri belirten bir hata döndürür ve **errno** ya da ayarlamak **ENOMEM**, ayırmak için yeterli bellek olduğunu belirten *maxlen* bayt (olduğunda bir **NULL** bağımsız değişken olarak verilen *arabellek*), veya **ERANGE**, yolun daha uzun olduğunu belirten *maxlen*  karakter.

Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Getcwd_dbg** ve **_wgetcwd_dbg** işlevleri aynı **_getcwd** ve **_wgetcwd** dışında ne zaman **_ Hata ayıklama** olan tanımlı, bu işlevleri hata ayıklama sürümü kullanma **malloc** ve **_malloc_dbg** , bellek ayırmak için **NULL** olarak geçirildi İlk parametre. Daha fazla bilgi için bkz: [_malloc_dbg](malloc-dbg.md).

Çoğu durumda bu işlevleri açıkça çağırmak gerekmez. Bunun yerine, tanımlayabilirsiniz **_CRTDBG_MAP_ALLOC** bayrağı. Zaman **_CRTDBG_MAP_ALLOC** tanımlanır, çağrılar **_getcwd** ve **_wgetcwd** için eşleştirilir **_getcwd_dbg** ve **_ wgetcwd_dbg**, sırasıyla ile *blockType* kümesine **_NORMAL_BLOCK**. Bu nedenle, öbek taşı olarak işaretlemek istediğiniz sürece bu işlevleri açıkça çağırın gerekmez **_clıent_block**. Daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details).

## <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd_dbg**|**_getcwd_dbg**|**_getcwd_dbg**|**_wgetcwd_dbg**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getcwd_dbg**|\<crtdbg.h >|
|**_wgetcwd_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[Yığın ayırma işlevleri sürümleri hata ayıklama](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
