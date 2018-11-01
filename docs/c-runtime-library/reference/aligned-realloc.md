---
title: _aligned_realloc
ms.date: 11/04/2016
apiname:
- _aligned_realloc
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
- _aligned_realloc
- aligned_realloc
helpviewer_keywords:
- aligned_realloc function
- _aligned_realloc function
ms.assetid: 80ce96e8-6087-416f-88aa-4dbb8cb1d218
ms.openlocfilehash: 456d57eeebfd47a2133b8a5813b11aaf77a300a4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607384"
---
# <a name="alignedrealloc"></a>_aligned_realloc

İle ayrılan bir bellek bloğunu boyutunu değiştirir [_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md).

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
Geçerli bellek bloğu işaretçisi.

*Boyutu*<br/>
İstenen bellek ayırmasının boyutu.

*Hizalama*<br/>
Hizalama değeri 2'in tam sayı üssü olması gerekir.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_realloc** yeniden (ve muhtemelen taşınan) bellek bloğuna void bir işaretçi döndürür. Dönüş değeri **NULL** boyutu sıfırsa ve arabellek bağımsız değişken değil **NULL**, ya da blok verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa. Bu durumda, özgün blok serbest bırakılır. İkinci, özgün blok değiştirilmez. Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun şekilde hizalanması garanti bir depolama alanına işaret eder. Bir işaretçi bir türü void, kullanımı dışında bir tür dönüş değerini almak için.

Bu belleği yeniden tahsis ve bir blok hizalamasını değiştirmek için bir hatadır.

## <a name="remarks"></a>Açıklamalar

**_aligned_realloc** dayanır **malloc**. Kullanma hakkında daha fazla bilgi için **_aligned_offset_malloc**, bkz: [malloc](malloc.md).

Bu işlev ayarlar **errno** için **ENOMEM** bellek ayırma başarısız olursa veya istenen boyutu büyüktür **_HEAP_MAXREQ**. Hakkında daha fazla bilgi için **errno**, bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_realloc** kendi parametrelerini doğrular. Varsa *hizalama* güç değil açıklandığı gibi bu işlev 2, geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevi döndürür **NULL** ve ayarlar **errno** için **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_realloc**|\<malloc.h >|

## <a name="example"></a>Örnek

Daha fazla bilgi için [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
