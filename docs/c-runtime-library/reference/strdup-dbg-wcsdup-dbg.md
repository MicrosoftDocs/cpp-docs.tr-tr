---
title: _strdup_dbg, _wcsdup_dbg
ms.date: 11/04/2016
apiname:
- _strdup_dbg
- _wcsdup_dbg
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
- _wcsdup_dbg
- strdup_dbg
- _strdup_dbg
- wcsdup_dbg
helpviewer_keywords:
- _wcsdup_dbg function
- stdup_dbg function
- copying strings
- duplicating strings
- strings [C++], copying
- strings [C++], duplicating
- _strdup_dbg function
- wcsdup_dbg function
ms.assetid: 681db70c-d124-43ab-b83e-5eeea9035097
ms.openlocfilehash: 3092c27df1e39c7b719f6e7037efa202d29c9e81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531165"
---
# <a name="strdupdbg-wcsdupdbg"></a>_strdup_dbg, _wcsdup_dbg

Sürümleri [_strdup ve _wcsdup](strdup-wcsdup-mbsdup.md) hata ayıklama sürümünü kullanan **malloc**.

## <a name="syntax"></a>Sözdizimi

```C
char *_strdup_dbg(
   const char *strSource,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wcsdup_dbg(
   const wchar_t *strSource,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*strSource*<br/>
Null ile sonlandırılmış kaynak dizesi.

*blockType*<br/>
İstenen bellek bloğu türü: **_clıent_block** veya **_NORMAL_BLOCK**.

*Dosya adı*<br/>
Ayırma işlemi istenen kaynak dosyasının adı işaretçi veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyada ayırma işlemi burada istendi veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri depolama konumuna kopyalanan dize için bir işaretçi döndürür veya **NULL** depolama ayırdığınızda.

## <a name="remarks"></a>Açıklamalar

**_Strdup_dbg** ve **_wcsdup_dbg** işlevleri aynı **_strdup** ve **_wcsdup** dışında olduğunda **_ Hata ayıklama** olan tanımlanan, bu işlevlerin hata ayıklama sürümünü kullanmak **malloc**, **_malloc_dbg**, yinelenen dize için bellek ayrılamadı. Hata ayıklama özellikleri hakkında bilgi için **_malloc_dbg**, bkz: [_malloc_dbg](malloc-dbg.md).

Bu işlevler, çoğu durumda açıkça çağırmanız gerekmez. Bunun yerine, bayrak tanımlayabilirsiniz **_CRTDBG_MAP_ALLOC**. Zaman **_CRTDBG_MAP_ALLOC** tanımlanır, çağrılar **_strdup** ve **_wcsdup** için eşleştirilir **_strdup_dbg** ve **_ wcsdup_dbg**sırasıyla ile *blockType* kümesine **_NORMAL_BLOCK**. Bu nedenle, yığın blokları olarak işaretlemek istediğiniz sürece bu işlevler açıkça çağırmanız gerekmez **_clıent_block**. Blok türleri hakkında daha fazla bilgi için bkz. [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsdup_dbg**|**_strdup_dbg**|**_mbsdup**|**_wcsdup_dbg**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strdup_dbg**, **_wcsdup_dbg**|\<crtdbg.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strdup, _wcsdup, _mbsdup](strdup-wcsdup-mbsdup.md)<br/>
[Öbek Atama İşlevleri Hata Ayıklama Sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
