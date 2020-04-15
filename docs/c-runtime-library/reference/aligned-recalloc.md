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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: af12322742c777cda879e01cb9c054297f807725
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350499"
---
# <a name="_aligned_recalloc"></a>_aligned_recalloc

[_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) ile ayrılan bellek bloğunun boyutunu değiştirir ve belleği 0'a başharfe ayırır.

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
Geçerli bellek blok işaretçisi.

*number*<br/>
Öğelerin sayısı.

*Boyutu*<br/>
Her öğenin bayt boyutu.

*Hizalama*<br/>
2'lik bir karşımat güç olması gereken hizalama değeri.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_recalloc,** geçersiz bir işaretçiyi yeniden tahsis edilen (ve büyük olasılıkla taşınan) bellek bloğuna döndürür. Boyut sıfır sayılsa ve arabellek bağımsız değişkeni **NULL**değilse veya bloğu verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, iade değeri **NULL'dur.** İlk durumda, özgün blok serbest bırakılır. İkinci durumda, özgün blok değişmez. İade değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalanması garanti edilen bir depolama alanına işaret ediyor. Bir işaretçiyi boşluktan başka bir türe almak için, iade değerinde bir tür döküm kullanın.

Belleği yeniden tahsis etmek ve bir bloğun hizasını değiştirmek bir hatadır.

## <a name="remarks"></a>Açıklamalar

**_aligned_recalloc** **malloc**dayanmaktadır. **_aligned_offset_malloc**kullanma hakkında daha fazla bilgi için, [bkz.](malloc.md)

Bu işlev, bellek ayırma başarısız olursa veya istenen boyut **_HEAP_MAXREQ**büyükse **ENOM'a** **errno** ayarlar. **errno**hakkında daha fazla bilgi için, [bkz. errno, _doserrno, _sys_errlist, ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_recalloc** parametrelerini doğrular. *Hizalama* 2'nin bir gücü değilse, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, bu işlev **NULL** döndürür ve **EINVAL** **için errno** ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_recalloc**|\<malloc.h>|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
[_recalloc](recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
