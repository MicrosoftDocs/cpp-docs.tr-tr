---
title: _tempnam_dbg, _wtempnam_dbg
ms.date: 11/04/2016
apiname:
- _wtempnam_dbg
- _tempnam_dbg
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
- wtempnam_dbg
- tempnam_dbg
- _tempnam_dbg
- _wtempnam_dbg
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
ms.openlocfilehash: 804c8ad1f17c6ee1df563cafc69ee7aef494d1cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258142"
---
# <a name="tempnamdbg-wtempnamdbg"></a>_tempnam_dbg, _wtempnam_dbg

İşlev sürümleri [_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) hata ayıklama sürümünü kullanan **malloc**, **_malloc_dbg**.

## <a name="syntax"></a>Sözdizimi

```C
char *_tempnam_dbg(
   const char *dir,
   const char *prefix,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wtempnam_dbg(
   const wchar_t *dir,
   const wchar_t *prefix,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*dizini*<br/>
Dosya adında hiçbir TMP ortam değişkeni yoksa veya TMP geçerli bir dizin değil ise kullanılan yol.

*prefix*<br/>
Bekletilen tarafından döndürülen adlarına olacak dize **_tempnam**.

*blockType*<br/>
İstenen bellek bloğu türü: **_clıent_block** veya **_NORMAL_BLOCK**.

*Dosya adı*<br/>
Ayırma işlemi istenen kaynak dosyasının adı işaretçi veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyada ayırma işlemi burada istendi veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

Her işlev oluşturulan adı için bir işaretçi döndürür veya **NULL** bir hata varsa. Belirtilen TMP ortam değişkenini ve içinde geçersiz dizin adı yoksa hata meydana gelebilir *dir* parametresi.

> [!NOTE]
> **Ücretsiz** (veya **free_dbg**) tarafından ayrılan işaretçiler için çağrılması gerekmez **_tempnam_dbg** ve **_wtempnam_dbg**.

## <a name="remarks"></a>Açıklamalar

**_Tempnam_dbg** ve **_wtempnam_dbg** işlevleri aynı **_tempnam** ve **_wtempnam** dışında olduğunda **_DEBUG** olan tanımlanan, bu işlevlerin hata ayıklama sürümünü kullanmak **malloc** ve **_malloc_dbg**, bellek ayırmak için **NULL** olduğu İlk parametre olarak geçirildi. Daha fazla bilgi için [_malloc_dbg](malloc-dbg.md).

Bu işlevler, çoğu durumda açıkça çağırmanız gerekmez. Bunun yerine, bayrak tanımlayabilirsiniz **_CRTDBG_MAP_ALLOC**. Zaman **_CRTDBG_MAP_ALLOC** tanımlanır, çağrılar **_tempnam** ve **_wtempnam** için eşleştirilir **_tempnam_dbg** ve **_ wtempnam_dbg**sırasıyla ile *blockType* kümesine **_NORMAL_BLOCK**. Bu nedenle, yığın blokları olarak işaretlemek istediğiniz sürece bu işlevler açıkça çağırmanız gerekmez **_clıent_block**. Daha fazla bilgi için [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttempnam_dbg**|**_tempnam_dbg**|**_tempnam_dbg**|**_wtempnam_dbg**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_tempnam_dbg**, **_wtempnam_dbg**|\<crtdbg.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[Öbek Atama İşlevleri Hata Ayıklama Sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
