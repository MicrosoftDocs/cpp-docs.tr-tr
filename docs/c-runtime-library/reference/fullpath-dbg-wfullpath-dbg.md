---
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
ms.openlocfilehash: 9271e26bcf4a78ff8d2e4fcf108f1e483c22c1d7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956307"
---
# <a name="_fullpath_dbg-_wfullpath_dbg"></a>_fullpath_dbg, _wfullpath_dbg

[_Fullpath, _wfullpath 'in,](fullpath-wfullpath.md) bellek ayırmak için **malloc** hata ayıklama sürümünü kullanan sürümleri.

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
Mutlak veya tam yol adı veya **null**içeren bir arabelleğin işaretçisi.

*relPath*<br/>
Göreli yol adı.

*'In*<br/>
Mutlak yol adı arabelleğinin (*absPath*) uzunluk üst sınırı. Bu uzunluk **_fullpath** için bayt, ancak **_wfullpath**için de geniş karakterler (**wchar_t**) cinsinden.

*blockType*<br/>
İstenen bellek bloğu türü: **_Client_block** veya **_NORMAL_BLOCK**.

*kısaltın*<br/>
Ayırma işlemi veya **null**için istenen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Ayırma işleminin istendiği veya **null**olduğu kaynak dosyadaki satır numarası.

## <a name="return-value"></a>Dönüş Değeri

Her işlev, mutlak yol adını (*absPath*) içeren bir arabelleğe bir işaretçi döndürür. Bir hata varsa (örneğin, *RelPath* içinde geçirilen değer geçerli olmayan veya bulunamayan bir sürücü harfi içeriyorsa veya oluşturulan mutlak yol adının (*absPath*) uzunluğu *MaxLength*'ten büyükse), işlev şunu döndürür  **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Fullpath_dbg** ve **_wfullpath_dbg** işlevleri **_fullpath** ve **_Wfullpath** ile aynıdır, ancak **_hata ayıklama** tanımlandığında, bu işlevler **malloc**, **_malloc_dbg**hata ayıklama sürümünü kullanır ilk parametre olarak **null** geçirilirse bellek ayırmak için. **_Malloc_dbg**hata ayıklama özellikleri hakkında daha fazla bilgi için, bkz. [_malloc_dbg](malloc-dbg.md).

Çoğu durumda bu işlevleri açıkça çağırmanız gerekmez. Bunun yerine, **_Crtdbg_map_ayırma** bayrağını tanımlayabilirsiniz. **_Crtdbg_map_ayırma** tanımlandığında, **_fullpath** ve **_wfullpath** çağrıları sırasıyla **_fullpath_dbg** ve **_Wfullpath_dbg**olarak eşlenir ve blok *türü* **_NORMAL_BLOCK**olarak ayarlanır. Bu nedenle, yığın bloklarını **_Client_block**olarak işaretlemek istemediğiniz sürece bu işlevleri açıkça çağırmanız gerekmez. Daha fazla bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath_dbg**|**_fullpath_dbg**|**_fullpath_dbg**|**_wfullpath_dbg**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fullpath_dbg**|\<Crtdbg. h >|
|**_wfullpath_dbg**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[Öbek Atama İşlevleri Hata Ayıklama Sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
