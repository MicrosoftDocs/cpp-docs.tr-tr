---
description: 'Hakkında daha fazla bilgi edinin: _getcwd_dbg _wgetcwd_dbg'
title: _getcwd_dbg, _wgetcwd_dbg
ms.date: 11/04/2016
api_name:
- _wgetcwd_dbg
- _getcwd_dbg
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
- api-ms-win-crt-environment-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getcwd_dbg
- _wgetcwd_dbg
- getcwd_dbg
- wgetcwd_dbg
helpviewer_keywords:
- wgetcwd_dbg function
- working directory
- _getcwd_dbg function
- getcwd_dbg function
- current working directory
- _wgetcwd_dbg function
- directories [C++], current working
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
ms.openlocfilehash: e470402cc258bf0fa0512136229eeace5bac466e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97256607"
---
# <a name="_getcwd_dbg-_wgetcwd_dbg"></a>_getcwd_dbg, _wgetcwd_dbg

[_Getcwd, _wgetcwd](getcwd-wgetcwd.md) işlevlerinin hata ayıklama sürümleri (yalnızca hata ayıklama sırasında kullanılabilir).

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

*arabelleğin*<br/>
Yol için depolama konumu.

*maxlen*<br/>
Karakter cinsinden yolun en fazla uzunluğu: **`char`** **_getcwd_dbg** için ve **`wchar_t`** **_wgetcwd_dbg**.

*Blok türü*<br/>
İstenen bellek bloğunun türü: **_CLIENT_BLOCK** veya **_NORMAL_BLOCK**.

*filename*<br/>
Ayırma işlemini veya **null değerini** isteyen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Ayırma işleminin istendiği veya **null** olduğu kaynak dosyadaki satır numarası.

## <a name="return-value"></a>Dönüş Değeri

*Arabelleğe* yönelik bir işaretçi döndürür. **Null** dönüş değeri bir hata olduğunu gösterir ve **errno** **değeri,** *maxlen* bayt ( **null** bir bağımsız değişken *buffer* olarak verildiğinde) veya **ERANGE** için, yolun *maxlen* karakterden daha uzun olduğunu belirten bir yetersiz bellek olduğunu gösterir.

Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Getcwd_dbg** ve **_wgetcwd_dbg** işlevleri **_getcwd** ve **_wgetcwd** aynıdır, ancak **_DEBUG** tanımlandığında bu işlevler, **NULL** değeri ilk parametre olarak geçirilirse bellek ayırmak için **malloc** ve **_malloc_dbg** hata ayıklama sürümünü kullanır. Daha fazla bilgi için bkz. [_malloc_dbg](malloc-dbg.md).

Çoğu durumda bu işlevleri açıkça çağırmanız gerekmez. Bunun yerine **_CRTDBG_MAP_ALLOC** bayrağını tanımlayabilirsiniz. **_CRTDBG_MAP_ALLOC** tanımlandığında, **_getcwd** ve **_Wgetcwd** çağrıları, sırasıyla *blok türü* **_wgetcwd_dbg** olarak ayarlanan **_getcwd_dbg** ve **_NORMAL_BLOCK** eşleştirilir. Bu nedenle, yığın bloklarını **_CLIENT_BLOCK** olarak işaretlemek istemediğiniz sürece bu işlevleri açıkça çağırmanız gerekmez. Daha fazla bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details).

## <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd_dbg**|**_getcwd_dbg**|**_getcwd_dbg**|**_wgetcwd_dbg**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getcwd_dbg**|\<crtdbg.h>|
|**_wgetcwd_dbg**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[Dizin denetimi](../../c-runtime-library/directory-control.md)<br/>
[Yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
