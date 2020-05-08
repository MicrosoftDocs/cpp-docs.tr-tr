---
title: _aligned_offset_realloc
ms.date: 4/2/2020
api_name:
- _aligned_offset_realloc
- _o__aligned_offset_realloc
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
- aligned_offset_realloc
- _aligned_offset_realloc
helpviewer_keywords:
- aligned_offset_realloc function
- _aligned_offset_realloc function
ms.assetid: e0263533-991e-41b0-acc9-1b8a51ab9ecd
ms.openlocfilehash: c719f62a089b1c233bac193f3431d0375af826eb
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910257"
---
# <a name="_aligned_offset_realloc"></a>_aligned_offset_realloc

[_Aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md)ile ayrılmış bir bellek bloğunun boyutunu değiştirir.

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_offset_realloc(
   void *memblock,
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Geçerli bellek bloğu işaretçisi.

*boyutla*<br/>
Bellek ayırmasının boyutu.

*hizalar*<br/>
2 ' nin tam sayı üssü olması gereken hizalama değeri.

*konumu*<br/>
Hizalamayı zorlamak için bellek ayırmaya olan fark.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_offset_realloc** , yeniden ayrılan (ve muhtemelen taşınan) bellek bloğuna void bir işaretçi döndürür. Boyut sıfır ise ve arabellek bağımsız değişkeni **null**olmadığında veya bloğu belirtilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa dönüş değeri **null** olur. İlk durumda, orijinal blok serbest bırakılır. İkinci durumda, orijinal blok değiştirilmez. Dönüş değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalı olarak garantili bir depolama alanına işaret eder. Void dışında bir türe işaretçi almak için, dönüş değerinde bir tür dönüştürme kullanın.

**_aligned_offset_realloc** , `__declspec(noalias)` ve `__declspec(restrict)`işlevin genel değişkenleri değiştirmeyeceği ve döndürülen işaretçinin diğer ad olmadığından garanti edilen anlamına gelir. Daha fazla bilgi için bkz. [noalias](../../cpp/noalias.md) ve [Restrict](../../cpp/restrict.md).

## <a name="remarks"></a>Açıklamalar

[_Aligned_offset_malloc](aligned-offset-malloc.md)gibi **_aligned_offset_realloc** , yapının yapı içindeki bir uzaklığa göre hizalanmasına olanak tanır.

**_aligned_offset_realloc** **malloc**'yi temel alır. **_Aligned_offset_malloc**kullanma hakkında daha fazla bilgi için bkz. [malloc](malloc.md). *Memblock* **null**ise, işlev dahili olarak **_aligned_offset_malloc** çağırır.

Bu işlev, bellek ayırma başarısız olursa veya istenen boyut **_HEAP_MAXREQ**fazlaysa, **errno** 'ı **ENOMEM** olarak ayarlar. **Errno**hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_offset_realloc** parametrelerini doğrular. *Hizalama* 2 ' nin üssü değilse veya Eğer değer *Boyut* ve sıfır dışında bir değere eşit veya *ondan büyükse,* bu işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **null** değerini döndürür ve **errno** 'ı **EINVAL**olarak ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_offset_realloc**|\<malloc. h>|

## <a name="example"></a>Örnek

Daha fazla bilgi için bkz. [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
