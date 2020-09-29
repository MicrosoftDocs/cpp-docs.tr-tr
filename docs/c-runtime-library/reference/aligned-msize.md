---
title: _aligned_msize
ms.date: 4/2/2020
api_name:
- _aligned_msize
- _o__aligned_msize
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _aligned_msize
- aligned_msize
helpviewer_keywords:
- aligned_msize function
- _aligned_msize function
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
ms.openlocfilehash: 1037c63af17a844959bc72e42da2c33267b43004
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414041"
---
# <a name="_aligned_msize"></a>_aligned_msize

Yığında ayrılan bellek bloğunun boyutunu döndürür.

## <a name="syntax"></a>Sözdizimi

```C
size_t _aligned_msize(
   void *memblock,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Bellek bloğunun işaretçisi.

*hizalar*<br/>
2 ' nin tam sayı üssü olması gereken hizalama değeri.

*konumu*<br/>
Hizalamayı zorlamak için bellek ayırmaya olan fark.

## <a name="return-value"></a>Dönüş Değeri

Boyutu (bayt olarak) işaretsiz bir tamsayı olarak döndürür.

## <a name="remarks"></a>Açıklamalar

**_Aligned_msize** işlevi, [_aligned_malloc](aligned-malloc.md) veya [_aligned_realloc](aligned-realloc.md)çağrısıyla ayrılan bellek bloğunun boyutunu bayt cinsinden döndürür. *Hizalama* ve *Aralık* değerleri, bloğu ayrılmış işleve geçirilen değerlerle aynı olmalıdır.

Uygulama, C çalışma zamanı kitaplıklarının bir hata ayıklama sürümü ile bağlantılı olduğunda **_aligned_msize** [_aligned_msize_dbg](aligned-msize-dbg.md)çözümlenir. Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

Bu işlev, parametresini doğrular. *Memblock* null işaretçisiyse veya *Hizalama* 2 ' nin üssü değilse, **_aligned_msize** [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre işleyicisini çağırır. Hata işlenirse, işlev **errno** ' ı **EINVAL** olarak ayarlar ve-1 döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_msize**|\<malloc.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek ayırma](../../c-runtime-library/memory-allocation.md)<br/>
