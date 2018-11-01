---
title: _aligned_offset_malloc
ms.date: 11/04/2016
apiname:
- _aligned_offset_malloc
apilocation:
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
apitype: DLLExport
f1_keywords:
- _aligned_offset_malloc
- aligned_offset_malloc
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
ms.openlocfilehash: 824edfd8bb96d805a030fb205dee62fa9eb4fd06
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644645"
---
# <a name="alignedoffsetmalloc"></a>_aligned_offset_malloc

Belirtilen hizalama sınırındaki belleği ayırır.

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
İstenen bellek ayırmasının boyutu.

*Hizalama*<br/>
Hizalama değeri 2'in tam sayı üssü olması gerekir.

*uzaklık*<br/>
Hizalama zorlamak için bellek ayırma olan uzaklık.

## <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek bloğuna işaretçi veya **NULL** işlemi başarısız.

## <a name="remarks"></a>Açıklamalar

**_aligned_offset_malloc** hizalama iç içe geçmiş bir öğede; gereken olduğu durumlarda kullanışlıdır örneğin hizalama yuvalanan bir sınıf gerekirse.

**_aligned_offset_malloc** dayanır **malloc**; daha fazla bilgi için bkz: [malloc](malloc.md).

**_aligned_offset_malloc** işaretlenmiş `__declspec(noalias)` ve `__declspec(restrict)`, işlevin genel değişkenleri sağlanır ve diğer ad verilmediğini göstermeyecektir işaretçi döndüren anlamına gelir. Daha fazla bilgi için [noalias](../../cpp/noalias.md) ve [kısıtlama](../../cpp/restrict.md).

Bu işlev ayarlar **errno** için **ENOMEM** bellek ayırma başarısız olursa veya istenen boyutu büyüktür **_HEAP_MAXREQ**. Hakkında daha fazla bilgi için **errno**, bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_offset_malloc** kendi parametrelerini doğrular. Varsa *hizalama* 2'in kuvveti değil veya *uzaklığı* büyüktür veya eşittir *boyutu* ve sıfır değilse, bu işlev geçersiz parametre işleyicisi içindeaçıklananşekildeçağırır[ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevi döndürür **NULL** ve ayarlar **errno** için **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_offset_malloc**|\<malloc.h >|

## <a name="example"></a>Örnek

Daha fazla bilgi için [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
