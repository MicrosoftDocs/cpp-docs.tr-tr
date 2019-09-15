---
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
ms.openlocfilehash: 73642730995ac5c0b47519fac64b30400d47767c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946248"
---
# <a name="_tempnam_dbg-_wtempnam_dbg"></a>_tempnam_dbg, _wtempnam_dbg

[_Tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) 'in, **malloc**, **_malloc_dbg**hata ayıklama sürümünü kullanan işlev sürümleri.

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

*prefix*<br/>
**_Tempnam**tarafından döndürülen adlara önceden gönderilecek dize.

*blockType*<br/>
İstenen bellek bloğu türü: **_Client_block** veya **_NORMAL_BLOCK**.

*kısaltın*<br/>
Ayırma işlemi veya **null**için istenen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Kaynak dosyasındaki, ayırma işleminin istendiği veya **null**olduğu satır numarası.

## <a name="return-value"></a>Dönüş Değeri

Her işlev, bir hata varsa, oluşturulan veya **null** olan ada bir işaretçi döndürür. TMP ortam değişkeninde ve *dir* parametresinde geçersiz bir dizin adı belirtilmişse hata meydana gelebilir.

> [!NOTE]
> **ücretsiz** (veya **free_dbg**), **_tempnam_dbg** ve **_wtempnam_dbg**tarafından ayrılan işaretçiler için çağrılmalıdır.

## <a name="remarks"></a>Açıklamalar

**_Tempnam_dbg** ve **_wtempnam_dbg** işlevleri, **_tempnam** ve **_Wtempnam** ile aynıdır, ancak **_hata ayıklama** tanımlandığında, bu işlevler, için **malloc** ve **_malloc_dbg**hata ayıklama sürümünü kullanır ilk parametre olarak **null** geçirilirse bellek ayırır. Daha fazla bilgi için bkz. [_malloc_dbg](malloc-dbg.md).

Çoğu durumda bu işlevleri açıkça çağırmanız gerekmez. Bunun yerine, **_Crtdbg_map_polationbayrağını**tanımlayabilirsiniz. **_Crtdbg_map_ayırma** tanımlandığında, **_tempnam** ve **_wtempnam** çağrıları sırasıyla **_Tempnam_dbg** ve **_Wtempnam_dbg**ile eşleştirilir, *blok türü* **_NORMAL_BLOCK**olarak ayarlanır. Bu nedenle, yığın bloklarını **_Client_block**olarak işaretlemek istemediğiniz sürece bu işlevleri açıkça çağırmanız gerekmez. Daha fazla bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttempnam_dbg**|**_tempnam_dbg**|**_tempnam_dbg**|**_wtempnam_dbg**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_tempnam_dbg**, **_wtempnam_dbg**|\<Crtdbg. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[Öbek Atama İşlevleri Hata Ayıklama Sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
