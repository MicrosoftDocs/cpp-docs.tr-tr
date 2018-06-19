---
title: _wfullpath_dbg olan _fullpath_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _fullpath_dbg function
- relative file paths
- absolute paths
- fullpath_dbg function
- _wfullpath_dbg function
- wfullpath_dbg function
ms.assetid: 81f72f85-07da-4f5c-866a-598e0fb03f6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d04f3d7b53eca27d38a38b0bce284c17b15cae02
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34450901"
---
# <a name="fullpathdbg-wfullpathdbg"></a>_fullpath_dbg, _wfullpath_dbg

Sürümleri [_fullpath, _wfullpath](fullpath-wfullpath.md) hata ayıklama sürümünü kullanmak **malloc** bellek ayıramadı.

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
Mutlak veya tam yol adını içeren bir arabellek işaretçi veya **NULL**.

*relPath*<br/>
Göreli yol adı.

*maxLength*<br/>
Mutlak bir yol adı arabelleği maksimum uzunluğu (*absPath*). Bu uzunluğudur için bayt cinsinden **_fullpath** ancak geniş karakterler (**wchar_t**) için **_wfullpath**.

*blockType*<br/>
İstenen bellek bloğu türü: **_clıent_block** veya **_NORMAL_BLOCK**.

*Dosya adı*<br/>
İstenen ayırma işlemi kaynak dosyasının adını işaretçi veya **NULL**.

*LineNumber*<br/>
Satır numarası ayırma işlemi istenen burada kaynak dosyasında veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

Her işlevi bir işaretçi mutlak yol adı içeren bir arabellek döndürür (*absPath*). Bir hata varsa (örneğin, değer olarak aktarılırsa *relPath* geçersiz veya bulunamıyor, bir sürücü harfi içerir veya oluşturulan mutlak bir yol adının uzunluğu (*absPath*) büyüktür: *maxLength*) işlevi döndürür **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Fullpath_dbg** ve **_wfullpath_dbg** işlevleri aynı **_fullpath** ve **_wfullpath** dışında **_DEBUG** olan tanımlı, bu işlevleri hata ayıklama sürümü kullanma **malloc**, **_malloc_dbg**, bellek, ayırmak için **NULL** geçirilen İlk parametre olarak. Hata ayıklama özellikleri hakkında bilgi için **_malloc_dbg**, bkz: [_malloc_dbg](malloc-dbg.md).

Çoğu durumda bu işlevleri açıkça çağırmak gerekmez. Bunun yerine, tanımlayabilirsiniz **_CRTDBG_MAP_ALLOC** bayrağı. Zaman **_CRTDBG_MAP_ALLOC** tanımlanır, çağrılar **_fullpath** ve **_wfullpath** için eşleştirilir **_fullpath_dbg** ve **_wfullpath_dbg**, sırasıyla ile *blockType* kümesine **_NORMAL_BLOCK**. Bu nedenle, öbek taşı olarak işaretlemek istediğiniz sürece bu işlevleri açıkça çağırın gerekmez **_clıent_block**. Daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath_dbg**|**_fullpath_dbg**|**_fullpath_dbg**|**_wfullpath_dbg**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fullpath_dbg**|\<crtdbg.h >|
|**_wfullpath_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[Yığın ayırma işlevleri sürümleri hata ayıklama](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
