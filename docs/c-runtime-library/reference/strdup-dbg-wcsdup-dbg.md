---
title: _strdup_dbg, _wcsdup_dbg
ms.date: 11/04/2016
api_name:
- _strdup_dbg
- _wcsdup_dbg
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
ms.openlocfilehash: 9f7d4fd8781269ee37f7515fdcab72e5195fdf00
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958196"
---
# <a name="_strdup_dbg-_wcsdup_dbg"></a>_strdup_dbg, _wcsdup_dbg

**Malloc**'in hata ayıklama sürümünü kullanan [_strdup ve _wcsdup](strdup-wcsdup-mbsdup.md) sürümleri.

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
İstenen bellek bloğu türü: **_Client_block** veya **_NORMAL_BLOCK**.

*kısaltın*<br/>
Ayırma işlemi veya **null**için istenen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Kaynak dosyasındaki, ayırma işleminin istendiği veya **null**olduğu satır numarası.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, kopyalanmış dize için depolama konumuna bir işaretçi veya depolama alanı ayrılamadıysa **null** değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**_Strdup_dbg** ve **_wcsdup_dbg** işlevleri, **_strdup** ve **_wcsdup** ile **aynıdır; ancak** **_hata ayıklama** tanımlandığında, bu işlevler, ayırmak için **_malloc_dbg**hata ayıklama sürümünü kullanır Yinelenen dize için bellek. **_Malloc_dbg**hata ayıklama özellikleri hakkında daha fazla bilgi için, bkz. [_malloc_dbg](malloc-dbg.md).

Çoğu durumda bu işlevleri açıkça çağırmanız gerekmez. Bunun yerine, **_Crtdbg_map_polationbayrağını**tanımlayabilirsiniz. **_Crtdbg_map_ayırma** tanımlandığında, **_strdup** ve **_wcsdup** çağrıları sırasıyla **_strdup_dbg** ve **_Wcsdup_dbg**olarak eşlenir ve *blok türü* **_NORMAL_BLOCK**olarak ayarlanır. Bu nedenle, yığın bloklarını **_Client_block**olarak işaretlemek istemediğiniz sürece bu işlevleri açıkça çağırmanız gerekmez. Blok türleri hakkında daha fazla bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsdup_dbg**|**_strdup_dbg**|**_mbsdup**|**_wcsdup_dbg**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strdup_dbg**, **_wcsdup_dbg**|\<Crtdbg. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm hata ayıklama sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenleme](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strdup, _wcsdup, _mbsdup](strdup-wcsdup-mbsdup.md)<br/>
[Öbek Atama İşlevleri Hata Ayıklama Sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
