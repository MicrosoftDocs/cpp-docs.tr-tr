---
title: _getdcwd_dbg, _wgetdcwd_dbg
ms.date: 11/04/2016
apiname:
- _getdcwd_dbg
- _wgetdcwd_dbg
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
apitype: DLLExport
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
ms.openlocfilehash: 700cfe732dc390ca59a976694403bb3d91af5980
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547186"
---
# <a name="getdcwddbg-wgetdcwddbg"></a>_getdcwd_dbg, _wgetdcwd_dbg

Hata ayıklama sürümleri [_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md) işlevleri (yalnızca hata ayıklama sırasında kullanılabilir).

## <a name="syntax"></a>Sözdizimi

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

*Sürücü*<br/>
Diskin adı.

*Arabellek*<br/>
Yol için depolama konumu.

*maxlen*<br/>
Karakter cinsinden yolun en fazla uzunluk: **char** için **_getdcwd_dbg** ve **wchar_t** için **_wgetdcwd_dbg**.

*blockType*<br/>
İstenen bellek bloğu türü: **_clıent_block** veya **_NORMAL_BLOCK**.

*Dosya adı*<br/>
Ayırma işlemi istenen kaynak dosyasının adını işaretçisi veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyada ayırma işlemi burada istendi veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

Bir işaretçi döndürür *arabellek*. A **NULL** dönüş değeri bir hata gösterir ve **errno** ya da ayarlanmış **ENOMEM**, ayırmak için yeterli bellek olduğunu belirten *maxlen* bayt (zaman bir **NULL** bağımsız değişken olarak verilir *arabellek*), veya **ERANGE**, yolun daha uzun olduğunu belirten *maxlen*  karakter. Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Getdcwd_dbg** ve **_wgetdcwd_dbg** işlevleri aynı **_getdcwd** ve **_wgetdcwd** dışında olduğunda **_DEBUG** olan tanımlanan, bu işlevlerin hata ayıklama sürümünü kullanmak **malloc** ve **_malloc_dbg** , bellek ayırmak için **NULL** geçirilir olarak *arabellek* parametresi. Daha fazla bilgi için [_malloc_dbg](malloc-dbg.md).

Bu işlevler, çoğu durumda açıkça çağırmanız gerekmez. Bunun yerine, tanımlayabileceğiniz **_CRTDBG_MAP_ALLOC** bayrağı. Zaman **_CRTDBG_MAP_ALLOC** tanımlanır, çağrılar **_getdcwd** ve **_wgetdcwd** için eşleştirilir **_getdcwd_dbg** ve **_ wgetdcwd_dbg**sırasıyla ile *blockType* kümesine **_NORMAL_BLOCK**. Bu nedenle, yığın blokları olarak işaretlemek istediğiniz sürece bu işlevler açıkça çağırmanız gerekmez **_clıent_block**. Daha fazla bilgi için [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd_dbg**|**_getdcwd_dbg**|**_getdcwd_dbg**|**_wgetdcwd_dbg**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getdcwd_dbg**|\<crtdbg.h >|
|**_wgetdcwd_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[Öbek Atama İşlevleri Hata Ayıklama Sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
