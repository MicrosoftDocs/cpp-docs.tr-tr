---
title: _getcwd_dbg, _wgetcwd_dbg
ms.date: 11/04/2016
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
helpviewer_keywords:
- wgetcwd_dbg function
- working directory
- _getcwd_dbg function
- getcwd_dbg function
- current working directory
- _wgetcwd_dbg function
- directories [C++], current working
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
ms.openlocfilehash: 9616c5f7e29b4f003d3943ba058d1f1a1d5adb5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287234"
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
Karakter cinsinden yolun en fazla uzunluk: **char** için **_getcwd_dbg** ve **wchar_t** için **_wgetcwd_dbg**.

*blockType*<br/>
İstenen bellek bloğu türü: **_clıent_block** veya **_NORMAL_BLOCK**.

*Dosya adı*<br/>
Ayırma işlemi istenen kaynak dosyasının adını işaretçisi veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyada ayırma işlemi burada istendi veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

Bir işaretçi döndürür *arabellek*. A **NULL** dönüş değeri bir hata gösterir ve **errno** ya da ayarlanmış **ENOMEM**, ayırmak için yeterli bellek olduğunu belirten *maxlen* bayt (zaman bir **NULL** bağımsız değişken olarak verilir *arabellek*), veya **ERANGE**, yolun daha uzun olduğunu belirten *maxlen*  karakter.

Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Getcwd_dbg** ve **_wgetcwd_dbg** işlevleri aynı **_getcwd** ve **_wgetcwd** dışında olduğunda **_ Hata ayıklama** olan tanımlanan, bu işlevlerin hata ayıklama sürümünü kullanmak **malloc** ve **_malloc_dbg** , bellek ayırmak için **NULL** olarak geçirilir İlk parametre. Daha fazla bilgi için [_malloc_dbg](malloc-dbg.md).

Bu işlevler, çoğu durumda açıkça çağırmanız gerekmez. Bunun yerine, tanımlayabileceğiniz **_CRTDBG_MAP_ALLOC** bayrağı. Zaman **_CRTDBG_MAP_ALLOC** tanımlanır, çağrılar **_getcwd** ve **_wgetcwd** için eşleştirilir **_getcwd_dbg** ve **_ wgetcwd_dbg**sırasıyla ile *blockType* kümesine **_NORMAL_BLOCK**. Bu nedenle, yığın blokları olarak işaretlemek istediğiniz sürece bu işlevler açıkça çağırmanız gerekmez **_clıent_block**. Daha fazla bilgi için [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details).

## <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd_dbg**|**_getcwd_dbg**|**_getcwd_dbg**|**_wgetcwd_dbg**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getcwd_dbg**|\<crtdbg.h >|
|**_wgetcwd_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[Öbek Atama İşlevleri Hata Ayıklama Sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
