---
description: 'Hakkında daha fazla bilgi edinin: _tempnam_dbg _wtempnam_dbg'
title: _tempnam_dbg, _wtempnam_dbg
ms.date: 11/04/2016
api_name:
- _wtempnam_dbg
- _tempnam_dbg
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
ms.openlocfilehash: 0f8788eb00d6cfd19f5675824838ce37e905b8ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326216"
---
# <a name="_tempnam_dbg-_wtempnam_dbg"></a>_tempnam_dbg, _wtempnam_dbg

[_Tempnam, _wtempnam, tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) 'ın, **malloc** hata ayıklama sürümünü kullanan _wtmpnam işlev sürümleri **_malloc_dbg**.

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

*öğesini*<br/>
TMP ortam değişkeni yoksa veya TMP geçerli bir dizin değilse dosya adında kullanılan yol.

*koy*<br/>
**_Tempnam** tarafından döndürülen adlara ön bekletilen dize.

*Blok türü*<br/>
İstenen bellek bloğu türü: **_CLIENT_BLOCK** veya **_NORMAL_BLOCK**.

*filename*<br/>
Ayırma işlemi veya **null** için istenen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Kaynak dosyasındaki, ayırma işleminin istendiği veya **null** olduğu satır numarası.

## <a name="return-value"></a>Dönüş Değeri

Her işlev, bir hata varsa, oluşturulan veya **null** olan ada bir işaretçi döndürür. TMP ortam değişkeninde ve *dir* parametresinde geçersiz bir dizin adı belirtilmişse hata meydana gelebilir.

> [!NOTE]
> **_tempnam_dbg** ve **_wtempnam_dbg** tarafından ayrılan işaretçiler için **ücretsiz** (veya **free_dbg**) çağrılması gerekir.

## <a name="remarks"></a>Açıklamalar

**_Tempnam_dbg** ve **_wtempnam_dbg** işlevleri **_tempnam** ve **_wtempnam** aynıdır, ancak **_DEBUG** tanımlandığında bu işlevler, **NULL** değeri ilk parametre olarak geçirilirse bellek ayırmak için **malloc** ve **_malloc_dbg** hata ayıklama sürümünü kullanır. Daha fazla bilgi için bkz. [_malloc_dbg](malloc-dbg.md).

Çoğu durumda bu işlevleri açıkça çağırmanız gerekmez. Bunun yerine, bayrağını **_CRTDBG_MAP_ALLOC** tanımlayabilirsiniz. **_CRTDBG_MAP_ALLOC** tanımlandığında, **_tempnam** ve **_Wtempnam** çağrıları, sırasıyla *blok türü* **_wtempnam_dbg** olarak ayarlanan **_tempnam_dbg** ve **_NORMAL_BLOCK** eşleştirilir. Bu nedenle, yığın bloklarını **_CLIENT_BLOCK** olarak işaretlemek istemediğiniz sürece bu işlevleri açıkça çağırmanız gerekmez. Daha fazla bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttempnam_dbg**|**_tempnam_dbg**|**_tempnam_dbg**|**_wtempnam_dbg**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_tempnam_dbg**, **_wtempnam_dbg**|\<crtdbg.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[Yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
