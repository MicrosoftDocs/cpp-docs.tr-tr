---
title: _fullpath_dbg, _wfullpath_dbg
ms.date: 11/04/2016
apiname:
- _wfullpath_dbg
- _fullpath_dbg
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
ms.openlocfilehash: b84c5b77d0a9bfb298d4c597e372cd39a92441f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332955"
---
# <a name="fullpathdbg-wfullpathdbg"></a>_fullpath_dbg, _wfullpath_dbg

Sürümleri [_fullpath, _wfullpath](fullpath-wfullpath.md) hata ayıklama sürümünü kullanan **malloc** bellek ayrılamadı.

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
Mutlak ya da tam yol adını içeren bir arabellek için işaretçi veya **NULL**.

*relPath*<br/>
Göreli yol adı.

*maxLength*<br/>
Mutlak yol adı arabelleği uzunluğu en fazla (*absPath*). Bu süre için bayt cinsinden olduğunu **_fullpath** ancak geniş karakterler (**wchar_t**) için **_wfullpath**.

*blockType*<br/>
İstenen bellek bloğu türü: **_clıent_block** veya **_NORMAL_BLOCK**.

*Dosya adı*<br/>
Ayırma işlemi istenen kaynak dosyasının adını işaretçisi veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyada ayırma işlemi burada istendi veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

Her işlevin mutlak yol adını içeren bir arabelleği için bir işaretçi döndürür (*absPath*). Bir hata varsa (örneğin, değer iletilmezse *relPath* geçersiz veya bulunamıyor, bir sürücü harfini içeren veya oluşturulan mutlak yol adının uzunluğu (*absPath*) büyüktür: *maxLength*) işlevi döndürür **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Fullpath_dbg** ve **_wfullpath_dbg** işlevleri aynı **_fullpath** ve **_wfullpath** dışında olduğunda **_DEBUG** olan tanımlanan, bu işlevlerin hata ayıklama sürümünü kullanmak **malloc**, **_malloc_dbg**, bellek ayırmak için **NULL** geçirilir İlk parametre olarak. Hata ayıklama özellikleri hakkında bilgi için **_malloc_dbg**, bkz: [_malloc_dbg](malloc-dbg.md).

Bu işlevler, çoğu durumda açıkça çağırmanız gerekmez. Bunun yerine, tanımlayabileceğiniz **_CRTDBG_MAP_ALLOC** bayrağı. Zaman **_CRTDBG_MAP_ALLOC** tanımlanır, çağrılar **_fullpath** ve **_wfullpath** için eşleştirilir **_fullpath_dbg** ve **_wfullpath_dbg**sırasıyla ile *blockType* kümesine **_NORMAL_BLOCK**. Bu nedenle, yığın blokları olarak işaretlemek istediğiniz sürece bu işlevler açıkça çağırmanız gerekmez **_clıent_block**. Daha fazla bilgi için [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath_dbg**|**_fullpath_dbg**|**_fullpath_dbg**|**_wfullpath_dbg**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fullpath_dbg**|\<crtdbg.h >|
|**_wfullpath_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[Öbek Atama İşlevleri Hata Ayıklama Sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
