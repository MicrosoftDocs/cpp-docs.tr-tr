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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 0a0dca94ec03286c92b3cbf1a51df59a1ca7af0c
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919483"
---
# <a name="_aligned_offset_malloc"></a>_aligned_offset_malloc

Belirtilen hizalama sınırında belleği ayırır.

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_offset_malloc(
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
İstenen bellek ayırmasının boyutu.

*hizalar*<br/>
2 ' nin tam sayı üssü olması gereken hizalama değeri.

*konumu*<br/>
Hizalamayı zorlamak için bellek ayırmaya olan fark.

## <a name="return-value"></a>Dönüş Değeri

İşlem başarısız olursa, ayrılan veya **null** olan bellek bloğunun işaretçisi.

## <a name="remarks"></a>Açıklamalar

**_aligned_offset_malloc** , iç içe yerleştirilmiş bir öğede hizalamanın gerekli olduğu durumlarda faydalıdır. Örneğin, iç içe yerleştirilmiş bir sınıfta hizalama gerekliyse.

**_aligned_offset_malloc** **malloc**'yi temel alır; daha fazla bilgi için bkz. [malloc](malloc.md).

**_aligned_offset_malloc** , `__declspec(noalias)` ve `__declspec(restrict)`işlevin genel değişkenleri değiştirmeyeceği ve döndürülen işaretçinin diğer ad olmadığından garanti edilen anlamına gelir. Daha fazla bilgi için bkz. [noalias](../../cpp/noalias.md) ve [Restrict](../../cpp/restrict.md).

Bu işlev, bellek ayırma başarısız olursa veya istenen boyut **_HEAP_MAXREQ**fazlaysa, **errno** 'ı **ENOMEM** olarak ayarlar. **Errno**hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_offset_malloc** parametrelerini doğrular. *Hizalama* 2 ' nin üssü değilse veya Eğer değer *Boyut* ve sıfır dışında bir değere eşit veya *ondan büyükse,* bu işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **null** değerini döndürür ve **errno** 'ı **EINVAL**olarak ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_offset_malloc**|\<malloc. h>|

## <a name="example"></a>Örnek

Daha fazla bilgi için bkz. [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
