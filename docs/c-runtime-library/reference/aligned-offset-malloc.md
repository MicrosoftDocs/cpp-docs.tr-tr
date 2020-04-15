---
title: _aligned_offset_malloc
ms.date: 4/2/2020
api_name:
- _aligned_offset_malloc
- _o__aligned_offset_malloc
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
- _aligned_offset_malloc
- aligned_offset_malloc
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
ms.openlocfilehash: 1f13afbab75d2926d1c642c1430a3ffe5ecbac8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350590"
---
# <a name="_aligned_offset_malloc"></a>_aligned_offset_malloc

Belleği belirli bir hizalama sınırına ayırır.

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_offset_malloc(
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
İstenen bellek ayırmanın boyutu.

*Hizalama*<br/>
2'lik bir karşımat güç olması gereken hizalama değeri.

*Uzaklık*<br/>
Hizalamazorlamak için bellek ayırma içine ofset.

## <a name="return-value"></a>Dönüş Değeri

İşlem başarısız olduysa ayrılan bellek bloğuna işaretçi veya **NULL.**

## <a name="remarks"></a>Açıklamalar

**_aligned_offset_malloc** iç içe bir öğe üzerinde hizalama gerekli olduğu durumlarda yararlıdır; örneğin, iç içe bir sınıfta hizalama gerekiyorsa.

**_aligned_offset_malloc** **malloc**dayanmaktadır; daha fazla bilgi için, [malloc](malloc.md)bakın.

**_aligned_offset_malloc** `__declspec(noalias)` işaretlenir `__declspec(restrict)`ve işlevin genel değişkenleri değiştirmemesi ve döndürülen işaretçinin diğer adı olmadığı anlamına gelir. Daha fazla bilgi için [noalias'a](../../cpp/noalias.md) bakın ve [kısıtlayın.](../../cpp/restrict.md)

Bu işlev, bellek ayırma başarısız olursa veya istenen boyut **_HEAP_MAXREQ**büyükse **ENOM'a** **errno** ayarlar. **errno**hakkında daha fazla bilgi için, [bkz. errno, _doserrno, _sys_errlist, ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_offset_malloc** parametrelerini doğrular. *Hizalama* 2'lik bir güç değilse veya *ofset* boyutundan büyük veya *boyuta* eşit sa ve sıfıra eşitse, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, bu işlev **NULL** döndürür ve **EINVAL** **için errno** ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_offset_malloc**|\<malloc.h>|

## <a name="example"></a>Örnek

Daha fazla bilgi için [_aligned_malloc.](aligned-malloc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
