---
title: _aligned_offset_recalloc
ms.date: 11/04/2016
apiname:
- _aligned_offset_recalloc
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
- aligned_offset_recalloc
- _aligned_offset_recalloc
helpviewer_keywords:
- aligned_offset_recalloc function
- _aligned_offset_recalloc function
ms.assetid: a258f54e-eeb4-4853-96fc-007d710f98e9
ms.openlocfilehash: 5ee163d257665b5481d6ab1ead54698ace1ef210
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561999"
---
# <a name="alignedoffsetrecalloc"></a>_aligned_offset_recalloc

İle ayrılan bir bellek bloğunu boyutunu değiştirir [_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) ve 0 belleği başlatır.

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

*Sayı*<br/>
Öğe sayısı.

*Boyutu*<br/>
Her öğenin bayt cinsinden uzunluğu.

*Hizalama*<br/>
Hizalama değeri 2'in tam sayı üssü olması gerekir.

*uzaklık*<br/>
Hizalama zorlamak için bellek ayırma olan uzaklık.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_offset_recalloc** yeniden (ve muhtemelen taşınan) bellek bloğuna void bir işaretçi döndürür. Dönüş değeri **NULL** boyutu sıfırsa ve arabellek bağımsız değişken değil **NULL**, ya da blok verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa. Bu durumda, özgün blok serbest bırakılır. İkinci durumda, özgün blok değiştirilmez. Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun şekilde hizalanması garanti bir depolama alanına işaret eder. Bir işaretçi bir türü void, kullanımı dışında bir tür dönüş değerini almak için.

**_aligned_offset_recalloc** işaretlenmiş `__declspec(noalias)` ve `__declspec(restrict)`, işlevin genel değişkenleri sağlanır ve diğer ad verilmediğini göstermeyecektir işaretçi döndüren anlamına gelir. Daha fazla bilgi için [noalias](../../cpp/noalias.md) ve [kısıtlama](../../cpp/restrict.md).

## <a name="remarks"></a>Açıklamalar

Gibi [_aligned_offset_malloc](aligned-offset-malloc.md), **_aligned_offset_recalloc** yapısı içinde bir uzaklık hizalanması için bir yapı sağlar.

**_aligned_offset_recalloc** dayanır **malloc**. Kullanma hakkında daha fazla bilgi için **_aligned_offset_malloc**, bkz: [malloc](malloc.md). Varsa *memblock* olduğu **NULL**, işlev çağrıları **_aligned_offset_malloc** dahili olarak.

Bu işlev ayarlar **errno** için **ENOMEM** bellek ayırma başarısız olursa veya istenen boyut (*numarası* * *boyutu* ) daha büyük **_HEAP_MAXREQ**. Hakkında daha fazla bilgi için **errno**, bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_offset_recalloc** kendi parametrelerini doğrular. Varsa *hizalama* 2'in kuvveti değil veya *uzaklığı* büyükse veya istenen boyutuna eşit ve sıfır değilse, bu işlev içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevi döndürür **NULL** ve ayarlar **errno** için **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_offset_recalloc**|\<malloc.h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
[_recalloc](recalloc.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
