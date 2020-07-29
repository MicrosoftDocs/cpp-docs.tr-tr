---
title: _getdcwd_dbg, _wgetdcwd_dbg
ms.date: 11/04/2016
api_name:
- _getdcwd_dbg
- _wgetdcwd_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getdcwd_dbg
- getdcwd_dbg
- _wgetdcwd_dbg
- wgetdcwd_dbg
helpviewer_keywords:
- working directory
- _getdcwd_dbg function
- wgetdcwd_dbg function
- current working directory
- getdcwd_dbg function
- _wgetdcwd_dbg function
- directories [C++], current working
ms.assetid: 266bf6f0-0417-497f-963d-2e0f306d9385
ms.openlocfilehash: a31617445ccb0640042be41ee4f710e528b9ceb7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229460"
---
# <a name="_getdcwd_dbg-_wgetdcwd_dbg"></a>_getdcwd_dbg, _wgetdcwd_dbg

[_Getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md) işlevlerinin hata ayıklama sürümleri (yalnızca hata ayıklama sırasında kullanılabilir).

## <a name="syntax"></a>Söz dizimi

```C
char *_getdcwd_dbg(
   int drive,
   char *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wgetdcwd_dbg(
   int drive,
   wchar_t *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*sürücü*<br/>
Disk sürücüsünün adı.

*arabelleğin*<br/>
Yol için depolama konumu.

*maxlen*<br/>
Karakter cinsinden yolun en fazla uzunluğu: **`char`** **_getdcwd_dbg** için ve **`wchar_t`** **_wgetdcwd_dbg**.

*Blok türü*<br/>
İstenen bellek bloğunun türü: **_CLIENT_BLOCK** veya **_NORMAL_BLOCK**.

*filename*<br/>
Ayırma işlemini veya **null değerini**isteyen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Ayırma işleminin istendiği veya **null**olduğu kaynak dosyadaki satır numarası.

## <a name="return-value"></a>Dönüş Değeri

*Arabelleğe*yönelik bir işaretçi döndürür. **Null** dönüş değeri bir hata olduğunu gösterir ve **errno** **değeri,** *maxlen* bayt ( **null** bir bağımsız değişken *buffer*olarak verildiğinde) veya **ERANGE**için, yolun *maxlen* karakterden daha uzun olduğunu belirten bir yetersiz bellek olduğunu gösterir. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Getdcwd_dbg** ve **_wgetdcwd_dbg** işlevleri **_getdcwd** ve **_wgetdcwd** aynıdır, ancak **_DEBUG** tanımlandığında bu işlevler, **null** *arabellek* parametresi olarak geçirilirse bellek ayırmak için **malloc** ve **_malloc_dbg** hata ayıklama sürümünü kullanır. Daha fazla bilgi için bkz. [_malloc_dbg](malloc-dbg.md).

Çoğu durumda bu işlevleri açıkça çağırmanız gerekmez. Bunun yerine **_CRTDBG_MAP_ALLOC** bayrağını tanımlayabilirsiniz. **_CRTDBG_MAP_ALLOC** tanımlandığında, **_getdcwd** ve **_Wgetdcwd** çağrıları, sırasıyla *blok türü* **_wgetdcwd_dbg**olarak ayarlanan **_getdcwd_dbg** ve **_NORMAL_BLOCK**eşleştirilir. Bu nedenle, yığın bloklarını **_CLIENT_BLOCK**olarak işaretlemek istemediğiniz sürece bu işlevleri açıkça çağırmanız gerekmez. Daha fazla bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd_dbg**|**_getdcwd_dbg**|**_getdcwd_dbg**|**_wgetdcwd_dbg**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getdcwd_dbg**|\<crtdbg.h>|
|**_wgetdcwd_dbg**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[Dizin denetimi](../../c-runtime-library/directory-control.md)<br/>
[Öbek Atama İşlevleri Hata Ayıklama Sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
