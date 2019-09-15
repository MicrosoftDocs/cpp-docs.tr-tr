---
title: _aligned_offset_recalloc
ms.date: 11/04/2016
api_name:
- _aligned_offset_recalloc
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
- aligned_offset_recalloc
- _aligned_offset_recalloc
helpviewer_keywords:
- aligned_offset_recalloc function
- _aligned_offset_recalloc function
ms.assetid: a258f54e-eeb4-4853-96fc-007d710f98e9
ms.openlocfilehash: ef8e68622c86e4504745a63cb0c2c3be4e916163
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944147"
---
# <a name="_aligned_offset_recalloc"></a>_aligned_offset_recalloc

[_Aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) ile ayrılmış bir bellek bloğunun boyutunu değiştirir ve belleği 0 olarak başlatır.

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_offset_recalloc(
   void *memblock,
   size_t num,
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Geçerli bellek bloğu işaretçisi.

*sayısından*<br/>
Öğe sayısı.

*boyutla*<br/>
Her öğenin bayt cinsinden uzunluğu.

*hizalar*<br/>
2 ' nin tam sayı üssü olması gereken hizalama değeri.

*konumu*<br/>
Hizalamayı zorlamak için bellek ayırmaya olan fark.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_offset_recalloc** , yeniden ayrılan (ve muhtemelen taşınan) bellek bloğuna void bir işaretçi döndürür. Boyut sıfır ise ve arabellek bağımsız değişkeni **null**olmadığında veya bloğu belirtilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa dönüş değeri **null** olur. İlk durumda, orijinal blok serbest bırakılır. İkinci durumda, orijinal blok değiştirilmez. Dönüş değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalı olarak garantili bir depolama alanına işaret eder. Void dışında bir türe işaretçi almak için, dönüş değerinde bir tür dönüştürme kullanın.

**_aligned_offset_recalloc** işaretlenir `__declspec(noalias)` ve `__declspec(restrict)`işlevin genel değişkenleri değiştirmeyeceği ve döndürülen işaretçinin diğer adı olmadığı anlamına gelir. Daha fazla bilgi için bkz. [noalias](../../cpp/noalias.md) ve [Restrict](../../cpp/restrict.md).

## <a name="remarks"></a>Açıklamalar

[_Aligned_offset_malloc](aligned-offset-malloc.md)gibi **_aligned_offset_recalloc** , yapının yapı içindeki bir uzaklığa göre hizalanmasına izin verir.

**_aligned_offset_recalloc** , **malloc**'yi temel alır. **_Aligned_offset_malloc**kullanma hakkında daha fazla bilgi için bkz. [malloc](malloc.md). *Memblock* **null**ise, işlev dahili olarak **_aligned_offset_malloc** çağırır.

Bu işlev, bellek ayırma başarısız olursa veya istenen boyut (*sayı* * *boyutu*) **_HEAP_MAXREQ**değerinden büyükse **errno** değerini **ENOMEM** olarak ayarlar. **Errno**hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_offset_recalloc** parametrelerini doğrular. *Hizalama* 2 ' nin üssü değilse veya *Aralık* istenen boyuttan büyük veya bu değere eşitse, bu işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **null** değerini döndürür ve **errno** 'ı **EINVAL**olarak ayarlar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_offset_recalloc**|\<malloc. h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
[_recalloc](recalloc.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
