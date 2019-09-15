---
title: _aligned_msize_dbg
ms.date: 11/04/2016
api_name:
- _aligned_msize_dbg
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
- _aligned_msize_dbg
helpviewer_keywords:
- _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
ms.openlocfilehash: f2a0ceab906dccacb2e1c78a8789d524b608a4ff
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939859"
---
# <a name="_aligned_msize_dbg"></a>_aligned_msize_dbg

Yığında ayrılan bellek bloğunun boyutunu döndürür (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
size_t _aligned_msize_dbg(
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

*Hizalama* ve *Aralık* değerleri, bloğu ayrılmış işleve geçirilen değerlerle aynı olmalıdır.

**_aligned_msize_dbg** , [_aligned_msize](aligned-msize.md) işlevinin bir hata ayıklama sürümüdür. [_Debug](../../c-runtime-library/debug.md) tanımlanmadığında, **_aligned_msize_dbg** 'e yapılan her çağrı, **_aligned_msize**çağrısına düşürülür. Hem **_aligned_msize** hem de **_aligned_msize_dbg** temel yığında bir bellek bloğunun boyutunu hesaplar, ancak **_aligned_msize_dbg** bir hata ayıklama özelliği ekler: Bu, döndürülen boyuttaki bellek bloğunun Kullanıcı bölümünün her iki tarafındaki arabellekleri da içerir.

Bu işlev, parametresini doğrular. *Memblock* null bir işaretçisiyse veya *Hizalama* 2 ' nin üssü değilse, **_msıze** [parametresi doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Hata işlenirse, işlev **errno** ' ı **EINVAL** olarak ayarlar ve-1 döndürür.

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde standart yığın işlevi çağırma ve hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_msize_dbg**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
