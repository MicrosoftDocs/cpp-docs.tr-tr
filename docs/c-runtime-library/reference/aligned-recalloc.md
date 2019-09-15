---
title: _aligned_recalloc
ms.date: 11/04/2016
api_name:
- _aligned_recalloc
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
- aligned_recalloc
- _aligned_recalloc
helpviewer_keywords:
- aligned_recalloc function
- _aligned_recalloc function
ms.assetid: d3da3dcc-79ef-4273-8af5-ac7469420142
ms.openlocfilehash: ef25769a04b27b02ccda16e86451a068ab0a0b84
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943774"
---
# <a name="_aligned_recalloc"></a>_aligned_recalloc

[_Aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) ile ayrılmış bir bellek bloğunun boyutunu değiştirir ve belleği 0 olarak başlatır.

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_recalloc(
   void *memblock,
   size_t num,
   size_t size,
   size_t alignment
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Geçerli bellek bloğu işaretçisi.

*sayısından*<br/>
Öğe sayısı.

*boyutla*<br/>
Her öğenin bayt cinsinden boyutu.

*hizalar*<br/>
2 ' nin tam sayı üssü olması gereken hizalama değeri.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_yeniden hesapla** , yeniden ayrılan (ve muhtemelen taşınan) bellek bloğuna void bir işaretçi döndürür. Boyut sıfır ise ve arabellek bağımsız değişkeni **null**olmadığında veya bloğu belirtilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa dönüş değeri **null** olur. İlk durumda, orijinal blok serbest bırakılır. İkinci durumda, orijinal blok değiştirilmez. Dönüş değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalı olarak garantili bir depolama alanına işaret eder. Void dışında bir türe işaretçi almak için, dönüş değerinde bir tür dönüştürme kullanın.

Belleği yeniden ayırmak ve bir bloğun hizalamasını değiştirmek hatadır.

## <a name="remarks"></a>Açıklamalar

**_aligned_yeniden hesapla** , **malloc**'yi temel alır. **_Aligned_offset_malloc**kullanma hakkında daha fazla bilgi için bkz. [malloc](malloc.md).

Bu işlev, bellek ayırma başarısız olursa veya istenen boyut **_Heap_maxreq**değerinden büyükse **errno** değerini **ENOMEM** olarak ayarlar. **Errno**hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_yeniden hesapla** parametrelerini doğrular. *Hizalama* 2 ' nin üssü değilse, bu Işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **null** değerini döndürür ve **errno** 'ı **EINVAL**olarak ayarlar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_recalloc**|\<malloc. h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
[_recalloc](recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
