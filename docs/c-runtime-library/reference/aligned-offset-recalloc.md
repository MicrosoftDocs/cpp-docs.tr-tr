---
title: _aligned_offset_recalloc
ms.date: 4/2/2020
api_name:
- _aligned_offset_recalloc
- _o__aligned_offset_recalloc
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
- aligned_offset_recalloc
- _aligned_offset_recalloc
helpviewer_keywords:
- aligned_offset_recalloc function
- _aligned_offset_recalloc function
ms.assetid: a258f54e-eeb4-4853-96fc-007d710f98e9
ms.openlocfilehash: 4c710712138d07191468cdc7ef02fc75e2f46dad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350551"
---
# <a name="_aligned_offset_recalloc"></a>_aligned_offset_recalloc

[_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) ile ayrılan bellek bloğunun boyutunu değiştirir ve belleği 0'a başharfe ayırır.

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
Geçerli bellek blok işaretçisi.

*number*<br/>
Öğe sayısı.

*Boyutu*<br/>
Her öğenin baytuzunluk.

*Hizalama*<br/>
2'lik bir karşımat güç olması gereken hizalama değeri.

*Uzaklık*<br/>
Hizalamazorlamak için bellek ayırma içine ofset.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_offset_recalloc,** geçersiz bir işaretçiyi yeniden tahsis edilen (ve büyük olasılıkla taşınan) bellek bloğuna döndürür. Boyut sıfır sayılsa ve arabellek bağımsız değişkeni **NULL**değilse veya bloğu verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, iade değeri **NULL'dur.** İlk durumda, özgün blok serbest bırakılır. İkinci durumda, özgün blok değişmez. İade değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalanması garanti edilen bir depolama alanına işaret ediyor. Bir işaretçiyi boşluktan başka bir türe almak için, iade değerinde bir tür döküm kullanın.

**_aligned_offset_recalloc** `__declspec(noalias)` işaretlenir `__declspec(restrict)`ve işlevin genel değişkenleri değiştirmemesi ve döndürülen işaretçinin diğer adı olmadığı anlamına gelir. Daha fazla bilgi için [noalias'a](../../cpp/noalias.md) bakın ve [kısıtlayın.](../../cpp/restrict.md)

## <a name="remarks"></a>Açıklamalar

[_aligned_offset_malloc](aligned-offset-malloc.md)gibi, **_aligned_offset_recalloc** yapının yapı içinde bir ofset hizalanmış olmasını sağlar.

**_aligned_offset_recalloc** **malloc**dayanmaktadır. **_aligned_offset_malloc**kullanma hakkında daha fazla bilgi için, [bkz.](malloc.md) *Memblock* **NULL**ise, işlev dahili **olarak _aligned_offset_malloc** çağırır.

Bu işlev, bellek ayırma başarısız olursa veya istenen boyut *(sayı* * *boyutu)* **_HEAP_MAXREQ**büyükse, **errno'yu** **ENOM** olarak ayarlar. **errno**hakkında daha fazla bilgi için, [bkz. errno, _doserrno, _sys_errlist, ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_offset_recalloc** parametrelerini doğrular. *Hizalama* 2'lik bir güç değilse veya *ofset* istenen boyuttan büyük veya eşitse ve sıfır sızıyorsa, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, bu işlev **NULL** döndürür ve **EINVAL** **için errno** ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_offset_recalloc**|\<malloc.h>|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
[_recalloc](recalloc.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
