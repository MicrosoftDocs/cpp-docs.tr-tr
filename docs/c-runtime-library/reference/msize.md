---
title: _msize
ms.date: 11/04/2016
api_name:
- _msize
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
ms.openlocfilehash: c1760cfa6a416e2eb4cd7b549cb5ae9bed00a609
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951431"
---
# <a name="_msize"></a>_msize

Yığında ayrılan bellek bloğunun boyutunu döndürür.

## <a name="syntax"></a>Sözdizimi

```C
size_t _msize(
   void *memblock
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Bellek bloğunun işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

**_msize** , (bayt olarak) boyutunu işaretsiz bir tamsayı olarak döndürür.

## <a name="remarks"></a>Açıklamalar

**_Msize** işlevi, **calloc**, **malloc**veya **realloc**çağrısıyla ayrılan bellek bloğunun boyutunu bayt cinsinden döndürür.

Uygulama, C çalışma zamanı kitaplıklarının bir hata ayıklama sürümüyle bağlandığında, **_msize** [_msize_dbg](msize-dbg.md)olarak çözümlenir. Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

Bu işlev, parametresini doğrular. *Memblock* null bir işaretçisiyse, **_Msıze** [parametresi doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Hata işlenirse, işlev **errno** ' ı **EINVAL** olarak ayarlar ve-1 döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_msize**|\<malloc. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

[Realloc](realloc.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[_expand](expand.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
