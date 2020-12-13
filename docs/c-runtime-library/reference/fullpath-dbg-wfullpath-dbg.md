---
description: 'Hakkında daha fazla bilgi edinin: _fullpath_dbg _wfullpath_dbg'
title: _fullpath_dbg, _wfullpath_dbg
ms.date: 11/04/2016
api_name:
- _wfullpath_dbg
- _fullpath_dbg
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
- wfullpath_dbg
- _wfullpath_dbg
- _fullpath_dbg
- fullpath_dbg
helpviewer_keywords:
- _fullpath_dbg function
- relative file paths
- absolute paths
- fullpath_dbg function
- _wfullpath_dbg function
- wfullpath_dbg function
ms.assetid: 81f72f85-07da-4f5c-866a-598e0fb03f6b
ms.openlocfilehash: a006533a6641110f1f94ca442743533c18c2aebb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334162"
---
# <a name="_fullpath_dbg-_wfullpath_dbg"></a>_fullpath_dbg, _wfullpath_dbg

_Fullpath sürümleri [,](fullpath-wfullpath.md) bellek ayırmak için **malloc** hata ayıklama sürümünü kullanan _wfullpath.

## <a name="syntax"></a>Sözdizimi

```C
char *_fullpath_dbg(
   char *absPath,
   const char *relPath,
   size_t maxLength,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wfullpath_dbg(
   wchar_t *absPath,
   const wchar_t *relPath,
   size_t maxLength,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*absPath*<br/>
Mutlak veya tam yol adı veya **null** içeren bir arabelleğin işaretçisi.

*relPath*<br/>
Göreli yol adı.

*'In*<br/>
Mutlak yol adı arabelleğinin (*absPath*) uzunluk üst sınırı. Bu uzunluk, **_fullpath** için bayt cinsinden, **`wchar_t`** **_wfullpath** için geniş karakterler () cinsinden.

*Blok türü*<br/>
İstenen bellek bloğu türü: **_CLIENT_BLOCK** veya **_NORMAL_BLOCK**.

*filename*<br/>
Ayırma işlemi veya **null** için istenen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Ayırma işleminin istendiği veya **null** olduğu kaynak dosyadaki satır numarası.

## <a name="return-value"></a>Dönüş Değeri

Her işlev, mutlak yol adını (*absPath*) içeren bir arabelleğe bir işaretçi döndürür. Bir hata varsa (örneğin, *RelPath* içinde geçirilen değer, geçerli olmayan veya bulunamayan bir sürücü harfi içeriyorsa veya oluşturulan mutlak yol adının (*absPath*) uzunluğu *MaxLength* değerinden büyükse, işlev **null** değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**_Fullpath_dbg** ve **_wfullpath_dbg** işlevleri **_fullpath** ve **_wfullpath** aynıdır, ancak **_DEBUG** tanımlandığında, bu işlevler, **NULL** değeri ilk parametre olarak geçirilirse bellek ayırmak için **malloc**, **_malloc_dbg** hata ayıklama sürümünü kullanır. **_Malloc_dbg** hata ayıklama özellikleri hakkında bilgi için bkz. [_malloc_dbg](malloc-dbg.md).

Çoğu durumda bu işlevleri açıkça çağırmanız gerekmez. Bunun yerine **_CRTDBG_MAP_ALLOC** bayrağını tanımlayabilirsiniz. **_CRTDBG_MAP_ALLOC** tanımlandığında, **_fullpath** ve **_Wfullpath** çağrıları, sırasıyla *blok türü* **_wfullpath_dbg** olarak ayarlanan **_fullpath_dbg** ve **_NORMAL_BLOCK** eşleştirilir. Bu nedenle, yığın bloklarını **_CLIENT_BLOCK** olarak işaretlemek istemediğiniz sürece bu işlevleri açıkça çağırmanız gerekmez. Daha fazla bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath_dbg**|**_fullpath_dbg**|**_fullpath_dbg**|**_wfullpath_dbg**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fullpath_dbg**|\<crtdbg.h>|
|**_wfullpath_dbg**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[Yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
