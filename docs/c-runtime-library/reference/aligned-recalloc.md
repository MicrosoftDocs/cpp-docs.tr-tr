---
title: _aligned_recalloc
ms.date: 4/2/2020
api_name:
- _aligned_recalloc
- _o__aligned_recalloc
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
- aligned_recalloc
- _aligned_recalloc
helpviewer_keywords:
- aligned_recalloc function
- _aligned_recalloc function
ms.assetid: d3da3dcc-79ef-4273-8af5-ac7469420142
ms.openlocfilehash: d425ff6c24cd7886c8d712b69e6e5d10da9dd6a2
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909806"
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

*number*<br/>
Öğe sayısı.

*boyutla*<br/>
Her öğenin bayt cinsinden boyutu.

*hizalar*<br/>
2 ' nin tam sayı üssü olması gereken hizalama değeri.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_recalloc** , yeniden ayrılan (ve muhtemelen taşınan) bellek bloğuna void bir işaretçi döndürür. Boyut sıfır ise ve arabellek bağımsız değişkeni **null**olmadığında veya bloğu belirtilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa dönüş değeri **null** olur. İlk durumda, orijinal blok serbest bırakılır. İkinci durumda, orijinal blok değiştirilmez. Dönüş değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalı olarak garantili bir depolama alanına işaret eder. Void dışında bir türe işaretçi almak için, dönüş değerinde bir tür dönüştürme kullanın.

Belleği yeniden ayırmak ve bir bloğun hizalamasını değiştirmek hatadır.

## <a name="remarks"></a>Açıklamalar

**_aligned_recalloc** **malloc**'yi temel alır. **_Aligned_offset_malloc**kullanma hakkında daha fazla bilgi için bkz. [malloc](malloc.md).

Bu işlev, bellek ayırma başarısız olursa veya istenen boyut **_HEAP_MAXREQ**fazlaysa, **errno** 'ı **ENOMEM** olarak ayarlar. **Errno**hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_recalloc** parametrelerini doğrular. *Hizalama* 2 ' nin üssü değilse, bu Işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **null** değerini döndürür ve **errno** 'ı **EINVAL**olarak ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_recalloc**|\<malloc. h>|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
[_recalloc](recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
