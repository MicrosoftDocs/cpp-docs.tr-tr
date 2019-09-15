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
ms.openlocfilehash: 8eb22f3716102c1b63b483e493eb44ac99228004
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955226"
---
# <a name="_getdcwd_dbg-_wgetdcwd_dbg"></a>_getdcwd_dbg, _wgetdcwd_dbg

[_Getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md) işlevlerinin hata ayıklama sürümleri (yalnızca hata ayıklama sırasında kullanılabilir).

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

*sürücü*<br/>
Disk sürücüsünün adı.

*arabelleğin*<br/>
Yol için depolama konumu.

*maxlen*<br/>
Saniyedeki yolun uzunluk üst sınırı: **_getdcwd_dbg** için **char** ve **_wgetdcwd_dbg**için **wchar_t** .

*blockType*<br/>
Bellek bloğunun istenen türü: **_Client_block** veya **_NORMAL_BLOCK**.

*kısaltın*<br/>
Ayırma işlemini veya **null değerini**isteyen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Ayırma işleminin istendiği veya **null**olduğu kaynak dosyadaki satır numarası.

## <a name="return-value"></a>Dönüş Değeri

*Arabelleğe*yönelik bir işaretçi döndürür. **Null** dönüş değeri bir hatayı gösterir ve **errno** , *maxlen* bayt ayırmak içinyeterli bellek olduğunu ( **null** bir bağımsız değişken *buffer*olarak verildiğinde) veya ERANGE olarak ayarlandığını belirten, yolun *maxlen* karakterden daha uzun olduğunu gösterir. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Getdcwd_dbg** ve **_wgetdcwd_dbg** işlevleri, **_getdcwd** ve **_wgetdcwd** ile aynıdır; ancak **_hata ayıklama** tanımlandığında, bu işlevler **malloc** ve **_malloc_dbg** hata ayıklama sürümünü kullanır *arabellek* parametresi olarak **null** geçirilirse bellek ayırır. Daha fazla bilgi için bkz. [_malloc_dbg](malloc-dbg.md).

Çoğu durumda bu işlevleri açıkça çağırmanız gerekmez. Bunun yerine, **_Crtdbg_map_ayırma** bayrağını tanımlayabilirsiniz. **_Crtdbg_map_ayırma** tanımlandığında, **_getdcwd** ve **_wgetdcwd** çağrıları sırasıyla **_getdcwd_dbg** ve **_Wgetdcwd_dbg**olarak eşlenir ve *blok türü* **_NORMAL_BLOCK**olarak ayarlanır. Bu nedenle, yığın bloklarını **_Client_block**olarak işaretlemek istemediğiniz sürece bu işlevleri açıkça çağırmanız gerekmez. Daha fazla bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd_dbg**|**_getdcwd_dbg**|**_getdcwd_dbg**|**_wgetdcwd_dbg**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getdcwd_dbg**|\<Crtdbg. h >|
|**_wgetdcwd_dbg**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[Öbek Atama İşlevleri Hata Ayıklama Sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
