---
title: _msize
ms.date: 4/2/2020
api_name:
- _msize
- _o__msize
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- msize
- _msize
helpviewer_keywords:
- memory blocks
- msize function
- _msize function
ms.assetid: 02b1f89e-d0d7-4f12-938a-9eeba48a0f88
ms.openlocfilehash: 7d5f62bd6111a305c18b0ee19bb6d3e90f2ddb49
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338662"
---
# <a name="_msize"></a>_msize

Yığında ayrılan bellek bloğu boyutunu döndürür.

## <a name="syntax"></a>Sözdizimi

```C
size_t _msize(
   void *memblock
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Bellek bloğuna işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_msize** boyutu (bayt içinde) imzasız bir tamsayı olarak döndürür.

## <a name="remarks"></a>Açıklamalar

**_msize** işlevi, **calloc,** **malloc**veya **realloc**için bir çağrı tarafından tahsis bellek bloğu, bayt, boyutunu döndürür.

Uygulama C çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı olduğunda, **_msize** [_msize_dbg.](msize-dbg.md) Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için [CRT Hata Ayıklama Yığını'na](/visualstudio/debugger/crt-debug-heap-details)bakın.

Bu işlev parametresini doğrular. *Memblock* null işaretçisi ise, **_msize** [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre işleyicisini çağırır. Hata işlenirse, işlev **errno'yu** **EINVAL'e** ayarlar ve -1 döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_msize**|\<malloc.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

[realloc](realloc.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[_expand](expand.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
