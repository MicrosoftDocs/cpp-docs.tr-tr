---
title: _aligned_realloc
ms.date: 4/2/2020
api_name:
- _aligned_realloc
- _o__aligned_realloc
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
- _aligned_realloc
- aligned_realloc
helpviewer_keywords:
- aligned_realloc function
- _aligned_realloc function
ms.assetid: 80ce96e8-6087-416f-88aa-4dbb8cb1d218
ms.openlocfilehash: 8b9dfae3fe7b17ad4ad28f69a36fbe0aa1c421e7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350512"
---
# <a name="_aligned_realloc"></a>_aligned_realloc

[_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md)ile ayrılan bellek bloğunun boyutunu değiştirir.

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_realloc(
   void *memblock,
   size_t size,
   size_t alignment
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Geçerli bellek blok işaretçisi.

*Boyutu*<br/>
İstenen bellek ayırmanın boyutu.

*Hizalama*<br/>
2'lik bir karşımat güç olması gereken hizalama değeri.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_realloc,** geçersiz bir işaretçiyi yeniden tahsis edilen (ve büyük olasılıkla taşınan) bellek bloğuna döndürür. Boyut sıfır sayılsa ve arabellek bağımsız değişkeni **NULL**değilse veya bloğu verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, iade değeri **NULL'dur.** İlk durumda, özgün blok serbest bırakılır. İkinci olarak, özgün blok değişmez. İade değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalanması garanti edilen bir depolama alanına işaret ediyor. Bir işaretçiyi boşluktan başka bir türe almak için, iade değerinde bir tür döküm kullanın.

Belleği yeniden tahsis etmek ve bir bloğun hizasını değiştirmek bir hatadır.

## <a name="remarks"></a>Açıklamalar

**_aligned_realloc** **malloc**dayanmaktadır. **_aligned_offset_malloc**kullanma hakkında daha fazla bilgi için, [bkz.](malloc.md)

Bu işlev, bellek ayırma başarısız olursa veya istenen boyut **_HEAP_MAXREQ**büyükse **ENOM'a** **errno** ayarlar. **errno**hakkında daha fazla bilgi için, [bkz. errno, _doserrno, _sys_errlist, ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_realloc** parametrelerini doğrular. *Hizalama* 2'nin bir gücü değilse, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, bu işlev **NULL** döndürür ve **EINVAL** **için errno** ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_realloc**|\<malloc.h>|

## <a name="example"></a>Örnek

Daha fazla bilgi için [_aligned_malloc.](aligned-malloc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
