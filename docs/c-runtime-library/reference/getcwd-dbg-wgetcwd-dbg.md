---
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
ms.openlocfilehash: 3eb318b9b2faa8716abdd26eafa926c8072b5614
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955289"
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
Saniyedeki yolun uzunluk üst sınırı: **_getcwd_dbg** için **char** ve **_wgetcwd_dbg**için **wchar_t** .

*blockType*<br/>
Bellek bloğunun istenen türü: **_Client_block** veya **_NORMAL_BLOCK**.

*kısaltın*<br/>
Ayırma işlemini veya **null değerini**isteyen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Ayırma işleminin istendiği veya **null**olduğu kaynak dosyadaki satır numarası.

## <a name="return-value"></a>Dönüş Değeri

*Arabelleğe*yönelik bir işaretçi döndürür. **Null** dönüş değeri bir hatayı gösterir ve **errno** , *maxlen* bayt ayırmak içinyeterli bellek olduğunu ( **null** bir bağımsız değişken *buffer*olarak verildiğinde) veya ERANGE olarak ayarlandığını belirten, yolun *maxlen* karakterden daha uzun olduğunu gösterir.

Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Getcwd_dbg** ve **_wgetcwd_dbg** işlevleri, **_getcwd** ve **_wgetcwd** ile aynıdır; ancak **_hata ayıklama** tanımlandığında, bu işlevler **malloc** ve **_malloc_dbg** hata ayıklama sürümünü kullanır ilk parametre olarak **null** geçirilirse bellek ayırır. Daha fazla bilgi için bkz. [_malloc_dbg](malloc-dbg.md).

Çoğu durumda bu işlevleri açıkça çağırmanız gerekmez. Bunun yerine, **_Crtdbg_map_ayırma** bayrağını tanımlayabilirsiniz. **_Crtdbg_map_ayırma** tanımlandığında, **_getcwd** ve **_wgetcwd** çağrıları sırasıyla **_getcwd_dbg** ve **_Wgetcwd_dbg**olarak eşlenir ve *blok türü* **_NORMAL_BLOCK**olarak ayarlanır. Bu nedenle, yığın bloklarını **_Client_block**olarak işaretlemek istemediğiniz sürece bu işlevleri açıkça çağırmanız gerekmez. Daha fazla bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details).

## <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd_dbg**|**_getcwd_dbg**|**_getcwd_dbg**|**_wgetcwd_dbg**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getcwd_dbg**|\<Crtdbg. h >|
|**_wgetcwd_dbg**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[Öbek Atama İşlevleri Hata Ayıklama Sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
